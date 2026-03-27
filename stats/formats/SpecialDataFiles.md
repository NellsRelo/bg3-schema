# Special Data Files

> **Path**: `Stats/Generated/Data/`
> **Packs**: Shared, SharedDev (most); some pack-specific

These files use unique formats distinct from the standard `new entry`/`type`/`data` pattern.

---

## BloodTypes.txt

**Format**: `new bloodtype "NAME", VFX1, VFX2, ..., VFX9`

Defines blood visual effects per creature type. Each entry is a single comma-separated line with 9 VFX references:

| Position | Purpose |
|----------|---------|
| 1 | Slash damage VFX |
| 2 | Piercing damage VFX |
| 3 | Bludgeoning damage VFX |
| 4 | Ground decal UUID (or empty) |
| 5 | Slash critical VFX |
| 6 | Piercing critical VFX |
| 7 | Bludgeoning critical VFX |
| 8 | Critical decal UUID (or empty) |
| 9 | Slash weapon blood VFX |

**Vanilla types**: Red, Silver, Green, Mithral, Acid, Fire, Water, Mud, Air, Black, Alcohol

**Packs**: Shared, SharedDev

---

## ItemColor.txt

**Format**: `new itemcolor "NAME", "HEX1", "HEX2", "HEX3"`

Defines named color palettes for item dyes. Three hex color values per entry (primary, shadow, highlight).

```
new itemcolor "Cobalt","2a4fd7","273b89","637fb7"
new itemcolor "Gold","e2bb00","8b6d00","ffdb7c"
new itemcolor "Mercury","909090","5b5b5b","c7c7c7"
```

**Vanilla colors**: Autunite, Burnished Bronze, Chalcocite, Cobalt, Droxlerite, Gold, Limonite, Malachite, Mercury, Pure Mythril, and more.

**Packs**: Shared, SharedDev

---

## Data.txt

**Format**: `key "NAME", "VALUE"`

Game configuration constants — numeric tuning values referenced by the engine.

```
key "NPC max combat turn time","20"
key "ThrowDistanceMin","3"
key "ThrowDistanceMax","18"
key "Sneak Damage Multiplier","1"
key "Haste Speed Modifier","1.5"
key "Slow Speed Modifier","0.8"
```

**Packs**: Shared, SharedDev

---

## XPData.txt

**Format**: `key "LevelN", "VALUE"` + `key "MaxXPLevel", "VALUE"`

Experience point thresholds per level.

```
key "Level1","300"
key "Level2","600"
key "Level3","1800"
key "Level4","3800"
key "Level5","6500"
key "MaxXPLevel","5"
```

**Packs**: Shared, SharedDev

---

## ItemProgressionNames.txt

**Format**: `new namegroup "NAME"` + `add name "HANDLE","SUFFIX"`

Defines localized display names for weapon progression tiers.

```
new namegroup "Club"
add name "h6e15582egd6bcg4894gbf01gf058808fd97d:1:Club",""

new namegroup "Dagger"
add name "hf529e688gc130g4f30gbf62g1459c3c0dab5:1:Dagger",""
```

Name handles use the format `handle:version:context`. The suffix is typically empty for base weapons.

**Packs**: Shared, SharedDev

---

## ItemProgressionVisuals.txt

**Format**: `new itemgroup "NAME"` + `add levelgroup` + `add rootgroup` + `add namegroup`

Associates visual templates and name groups with weapon progression tiers.

```
new itemgroup "Battleaxe"

add levelgroup 0,0,"All"
add rootgroup "a086b825-8f17-4f0e-855b-178f8cdc515a",""
add namegroup "Battleaxe","",""
```

| Keyword | Parameters | Purpose |
|---------|-----------|---------|
| `add levelgroup` | `MIN,MAX,"RARITY"` | Level range and rarity filter |
| `add rootgroup` | `"UUID",""` | RootTemplate UUID for the visual |
| `add namegroup` | `"NAME","",""` | References a namegroup from ItemProgressionNames.txt |

**Packs**: Shared, SharedDev
