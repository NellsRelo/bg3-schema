# Stats Entry Syntax & Inheritance Model

> How BG3 Stats entries (`new entry` / `type` / `using` / `data`) are defined, merged, and inherited across base game and mod files. Applies to **all** stats types: Weapon, Armor, SpellData, PassiveData, StatusData, Interrupt, etc.

---

## 1. Stats Entry Basics

Stats entries live in `.txt` files under `Stats/Generated/Data/`. They use a custom key-value format (NOT XML/LSX).

### 1.1 Syntax

```lua
new entry "EntryName"
type "EntryType"
using "ParentEntry"
data "FieldName" "FieldValue"
data "FieldName" "FieldValue"
```

| Keyword | Required | Purpose |
|---------|----------|---------|
| `new entry "Name"` | Yes | Declares or reopens an entry in the Lua state |
| `type "Type"` | Yes (first declaration) | Entry type: `Weapon`, `Armor`, `SpellData`, `PassiveData`, `StatusData`, `Interrupt`, etc. |
| `using "Parent"` | No | Copies all fields from `Parent` before applying this block's `data` lines |
| `data "Field" "Value"` | No | Sets or overrides a single field |

### 1.2 Entry Types and File Locations

| Type | Typical File(s) |
|------|-----------------|
| `Weapon` | `Weapon.txt` |
| `Armor` | `Armor.txt` |
| `SpellData` | `Spell_*.txt` (e.g., `Spell_Target.txt`, `Spell_Shout.txt`) |
| `PassiveData` | `Passive.txt` |
| `StatusData` | `Status_*.txt` |
| `Interrupt` | `Interrupt.txt` |
| `Object` | `Object.txt` |
| `Character` | `Character.txt` |

---

## 2. Inheritance via `using`

### 2.1 Basic Inheritance

`using` copies **all** fields from the parent entry, then explicit `data` lines override specific fields. This is a shallow merge — only fields explicitly set in the child block replace the parent's values; all other fields are retained as-is.

```lua
-- Parent defines a base dagger
new entry "WPN_Dagger"
type "Weapon"
data "Damage" "1d4"
data "Damage Type" "Piercing"
data "Weapon Properties" "Finesse;Light;Thrown;Melee"

-- Child inherits everything, overrides some fields
new entry "WPN_Dagger_1"
type "Weapon"
using "WPN_Dagger"
data "RootTemplate" "1eab180b-5bf9-48ea-aece-7ba20d1deb78"
data "Rarity" "Uncommon"
data "DefaultBoosts" "WeaponEnchantment(1);WeaponProperty(Magical)"
```

Result: `WPN_Dagger_1` has `Damage "1d4"` and `Damage Type "Piercing"` from its parent, plus its own `RootTemplate`, `Rarity`, and `DefaultBoosts`.

### 2.2 Cross-Type Restriction

`using` only works between entries of the **same type**. A `Weapon` entry cannot inherit from a `SpellData` entry.

### 2.3 Multi-Level Chains

Inheritance can chain: A → B → C. Each level copies from its resolved parent at the time of processing.

---

## 3. Multi-File Merge (Load Order Resolution)

This is the critical concept. Stats entries are accumulated into a **single Lua state** as files are processed. The game (and mods, which are just paks loaded in order) can define or redefine the same entry across multiple files. The engine processes them **in load order**, from scratch, every startup.

### 3.1 How It Works

When the engine encounters `new entry "X"`:

1. If entry `X` **does not exist** yet → create it fresh
2. If entry `X` **already exists** → reopen it for modification
3. If `using "X"` references **itself** (same name) → copies all current fields of `X` as the base, then applies new `data` lines on top
4. Explicit `data` lines **override** matching fields
5. Fields **not mentioned** in the new block are **preserved** from the previous state

### 3.2 Self-Referencing `using` (Mod Override Pattern)

A mod can modify an existing entry by declaring `new entry` with the same name and `using` that same name. This is the standard pattern for mod overrides:

```lua
-- In a mod loaded AFTER the base game:
new entry "WPN_Dagger_1"
type "Weapon"
using "WPN_Dagger_1"          -- inherits current state of WPN_Dagger_1
data "Rarity" "Rare"          -- overrides just this one field
```

This copies all existing fields of `WPN_Dagger_1` (as currently accumulated), then overrides only `Rarity`. Everything else is preserved.

### 3.3 Worked Example: Three-Mod Chain

**Mod 1 (base game)** — defines the entry:

```lua
new entry "WPN_Dagger_1"
type "Weapon"
using "WPN_Dagger"
data "RootTemplate" "1eab180b-5bf9-48ea-aece-7ba20d1deb78"
data "ValueUUID" "4cd41c74-9c86-4233-922e-4db5bc750df5"
data "ValueScale" "1"
data "Rarity" "Uncommon"
data "DefaultBoosts" "WeaponEnchantment(1);WeaponProperty(Magical)"
data "Weapon Properties" "Finesse;Light;Thrown;Melee;Dippable;Magical"
```

**Mod 2** — changes rarity to Rare and adds a passive:

```lua
new entry "WPN_Dagger_1"
type "Weapon"
using "WPN_Dagger_1"
data "Rarity" "Rare"
data "PassivesOnEquip" "MAG_Zhentarim_SleeperDagger_Passive"
```

After Mod 2 processes: entry has all Mod 1 fields, `Rarity` is now `"Rare"`, and `PassivesOnEquip` is set.

**Mod 3** — reverts rarity to Uncommon:

```lua
new entry "WPN_Dagger_1"
type "Weapon"
using "WPN_Dagger_1"
data "Rarity" "Uncommon"
```

After Mod 3 processes: `Rarity` is back to `"Uncommon"`, but `PassivesOnEquip` from Mod 2 **persists** because Mod 3 didn't touch it.

**Final resolved state** of `WPN_Dagger_1`:

```lua
new entry "WPN_Dagger_1"
type "Weapon"
using "WPN_Dagger"
data "RootTemplate" "1eab180b-5bf9-48ea-aece-7ba20d1deb78"
data "ValueUUID" "4cd41c74-9c86-4233-922e-4db5bc750df5"
data "ValueScale" "1"
data "Rarity" "Uncommon"
data "DefaultBoosts" "WeaponEnchantment(1);WeaponProperty(Magical)"
data "Weapon Properties" "Finesse;Light;Thrown;Melee;Dippable;Magical"
data "PassivesOnEquip" "MAG_Zhentarim_SleeperDagger_Passive"
```

### 3.4 Key Takeaways

| Rule | Detail |
|------|--------|
| **Additive** | Fields added by any mod in the chain persist unless explicitly overwritten by a later mod |
| **Last-write-wins** | For any given field, the last `data` line processed wins |
| **No implicit removal** | There is no way to "unset" a field — you can only overwrite it (e.g., set to empty `""`) |
| **Self-referencing `using`** | `using "X"` inside `new entry "X"` is idiomatic for mods; it snapshots the entry's current state |
| **Load order matters** | Mods processed later override earlier ones; base game files are just the first "mod" in the chain |
| **Per-startup resolution** | The full merge happens from scratch every game launch — there is no cached intermediate state |

---

## 4. Inheritance vs. Multi-File Merge

These are two distinct mechanisms that work together:

| Mechanism | Keyword | Purpose | Example |
|-----------|---------|---------|---------|
| **Inheritance** | `using "DifferentEntry"` | Create a new entry based on another entry's template | `WPN_Dagger_1` using `WPN_Dagger` |
| **Multi-file merge** | `using "SameEntry"` (self-ref) | Modify an existing entry from a later-loaded file | Mod overriding `WPN_Dagger_1` |

Both use the `using` keyword, but:
- **Inheritance** establishes a parent-child relationship between different entries
- **Multi-file merge** reopens and patches the same entry across files/mods

The resolution algorithm is identical in both cases: copy all fields from the referenced entry, then apply `data` overrides.

---

## 5. Applicability

This model is **not** specific to Weapons — it applies uniformly to all stats entry types:

- **SpellData**: Mods can override spell properties (costs, damage, range)
- **PassiveData**: Mods can modify passive effects
- **StatusData**: Mods can alter status durations, effects, icons
- **Armor**: Mods can change AC, proficiency requirements, boosts
- **Interrupt**: Mods can modify interrupt conditions and costs
- **Object / Character**: Same `using` + `data` override pattern

Any stats entry type that uses the `new entry` / `type` / `using` / `data` syntax follows the exact same inheritance and merge rules documented here.

---

## 6. Common Pitfalls

- **Forward references fail silently**: `using "Parent"` where `Parent` is defined later in the same file or in a later-loaded file will not inherit anything. The entry compiles without error but lacks inherited fields.
- **Empty string override**: Setting a field to `""` explicitly clears an inherited value. This is intentional for suppressing fields like `BoostsOnEquipMainHand`, but accidental empty overrides are a common source of bugs.
- **Case sensitivity in cross-format references**: Fields like `PassivesOnEquip` reference PassiveData entry names. These are **case-sensitive** — `"mypassive"` ≠ `"MyPassive"`. Mismatches link to nothing.
- **Whitespace in entry names**: Leading/trailing whitespace in `new entry "X "` (note trailing space) creates a different entry than `"X"`. Cross-references from LSX or other stats will fail to match.
- **Self-referencing `using` in base game files**: Don't use `using "X"` inside `new entry "X"` in your own mod's first definition. This pattern only works when overriding an entry that already exists from an earlier-loaded pak.
- There is a "Too many self inheritance" issue that can cause crashes

### Script Extender Override Alternative

For runtime-only changes, SE Lua can modify stats without file-level inheritance:

```lua
local stat = Ext.Stats.Get("WPN_Dagger_1")
stat.Rarity = "Legendary"
Ext.Stats.Sync("WPN_Dagger_1")  -- MUST sync
```

This bypasses load-order concerns entirely but only persists for the session.
