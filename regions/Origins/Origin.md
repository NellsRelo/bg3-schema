# Node: `Origin`

> **Region**: [Origins](_REGION.md)
> **Folder**: `Origins/`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | always | � | Primary key |
| `Name` | FixedString | always | `Generic`, `Astarion`, `Wyll`, `DarkUrge`, `Hireling_Barbarian` | Internal identifier |
| `DisplayName` | TranslatedString | always | handle + version | Localized name |
| `Description` | TranslatedString | always | handle + version | Localized description |
| `AvailableInCharacterCreation` | uint8 | always | `0` (hidden), `1` (playable), `2` (hireling) | **Not a bool** � 3 values |
| `AppearanceLocked` | bool | always | true/false | Whether appearance can be changed |
| `LockBody` | bool | common | true/false | Lock body type in CC |
| `LockRace` | bool | common | true/false | Lock race in CC |
| `LockClass` | bool | common | true/false | Lock class in CC |
| `BodyShape` | uint8 | always | `0` (Regular), `1` (Strong) | Body build |
| `BodyType` | uint8 | always | `0` (Masculine), `1` (Feminine) | Body type |
| `RaceUUID` | guid | common | links to Race.UUID | Default race |
| `SubRaceUUID` | guid | rare | sub-race UUID | Default sub-race |
| `ClassUUID` | guid | common | links to ClassDescription.UUID | Default class |
| `SubClassUUID` | guid | common | subclass UUID | Default subclass |
| `BackgroundUUID` | guid | common | links to Background.UUID | Default background |
| `VoiceTableUUID` | guid | common | voice set reference | Voice actor assignment |
| `GlobalTemplate` | guid | rare | template entity reference | RootTemplate link |
| `Identity` | uint8 | rare | Gender Identity | Identity category |
| `IsHenchman` | bool | rare | `true` | Marks as hireling |
| `Unique` | bool | common | true/false | Named companion flag |
| `ClassEquipmentOverride` | FixedString | rare | `EQ_Astarion`, `EQ_Wyll` | Custom starting equipment |
| `IntroDialogUUID` | guid | rare | intro dialog tree | First-meeting dialog |
| `CloseUpA` | LSString | rare | `ELF_M_Camera_Closeup_A` | Camera angle A |
| `CloseUpB` | LSString | rare | `ELF_M_Camera_Closeup_B` | Camera angle B |
| `GodUUID` | guid | rare | patron god UUID | Cleric deity selection |
| `Passives` | LSString | common | `DeathSavingThrows;BladeOfFrontiers` | **Semicolon-delimited** passives |
| `DefaultsTemplate` | guid | rare | character defaults template | |
| `ExcludesOriginUUID` | guid | rare | mutually exclusive origin | |

## Child Nodes

### AppearanceTags

Rare � visual appearance tag overrides.

| Attribute | Type | Frequency | Notes |
|-----------|------|-----------|-------|
| `Object` | guid | always | Tag UUID reference |

### ReallyTags

Common � gameplay-relevant tag classifications.

| Attribute | Type | Frequency | Notes |
|-----------|------|-----------|-------|
| `Object` | guid | always | Tag UUID reference |

## Patterns of Use

### Origin Categories

| Category | `AvailableInCharacterCreation` | `Unique` | `IsHenchman` | Source |
|----------|-------------------------------|----------|-------------|--------|
| Named companion | `1` | `true` | � | GustavDev |
| Dark Urge | `1` | `true` | � | GustavDev |
| Hireling | `2` | � | `true` | SharedDev |
| Generic player | `1` | � | � | Shared |
| Hidden NPC | `0` | varies | � | Gustav |

### Lock Fields

Named companions typically have `LockBody=true`, `LockRace=true`, `AppearanceLocked=true` since their appearance is canonical.

## Cross-References

| From | To | Via |
|------|----|-----|
| Origin.RaceUUID | [Race](../Races/Race.md) | Race.UUID |
| Origin.SubRaceUUID | [Race](../Races/Race.md) | Race.UUID (sub-race) |
| Origin.ClassUUID | [ClassDescription](../ClassDescriptions/ClassDescription.md) | ClassDescription.UUID |
| Origin.BackgroundUUID | [Background](../Backgrounds/Background.md) | Background.UUID |
| Origin.GodUUID | [God](../Gods/God.md) | God.UUID |
| Origin.VoiceTableUUID | [Voice](../Voices/Voice.md) | Voice.UUID |
| Origin.GlobalTemplate | [Templates](../Templates/_REGION.md) | GameObjects.MapKey |

## Caveats & Gotchas

- **AvailableInCharacterCreation is uint8, NOT bool** � `0`/`1`/`2` (hidden/playable/hireling). Using `true`/`false` will break parsing.
- **BodyShape vs BodyType** — These are separate fields. BodyType selects masculine (0) or feminine (1) body, BodyShape selects regular (0) or strong (1) build. Do not confuse them.
- **SubRaceUUID** � Not always present. Only used when the origin has a specific sub-race (e.g., High Elf vs just Elf).
- **Passives field** uses semicolons, consistent with Progression.PassivesAdded. These are **name-based references** (case-sensitive) to `Passive.txt` entries.
- **ExcludesOriginUUID** � Prevents selecting one origin if another is already in the party.
- **Split across sources** � Generic origin in Shared, hirelings in SharedDev, named companions in GustavDev/Gustav. Mods adding custom companions typically add to the Gustav-equivalent source.
- **ClassEquipmentOverride** � Overrides the class's default `ClassEquipment` from [ClassDescription](../ClassDescriptions/ClassDescription.md). This is a **name-based reference** to Equipment.txt.
- **GlobalTemplate** � UUID reference to a [GameObjects](../Templates/GameObjects.md) entry. This is the RootTemplate entity that represents the companion/hireling in-game. Without this, the origin has no physical presence.

## Data Flow for Custom Companions

Creating a custom companion requires coordinating across multiple regions:

```
Origin.lsx (this region)
+-- ClassUUID ? ClassDescription
+-- RaceUUID ? Race
+-- BackgroundUUID ? Background
+-- GodUUID ? God (clerics/paladins only)
+-- VoiceTableUUID ? Voice
+-- GlobalTemplate ? GameObjects (RootTemplate)
+-- ReallyTags ? Tags (gameplay classification)
+-- Passives ? Passive.txt (Stats TXT, name-based)
```

All UUID references must be valid. Missing localization handles cause `[...]` placeholders in-game.

## Scripting & Runtime Notes

- **Osiris events**: `CharacterJoinedParty`, `CharacterLeftParty`, `LeveledUp`, `Died`, `Resurrected` � all fire for origin characters.
- **SE**: `Ext.Entity` can query origin components. `Ext.Osiris.RegisterListener("CharacterJoinedParty", ...)` for party-related hooks.

## Similarities to Other Nodes

- [ClassDescription](../ClassDescriptions/ClassDescription.md) and [Race](../Races/Race.md) both have `ProgressionTableUUID` � Origins reference classes and races but don't have their own progression table.
- [Background](../Backgrounds/Background.md) also has `Tags` child nodes.
