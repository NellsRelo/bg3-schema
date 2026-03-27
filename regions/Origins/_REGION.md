# Region: `Origins`

> **Folder**: `Origins/`
> **Primary Node**: [Origin](Origin.md)
>
> Companions, hirelings, and the generic player origin. 30+ entries across sources.

---

## File Inventory

| Source | File | Entries | Notes |
|--------|------|---------|-------|
| Shared | Origins.lsx | 1 | Generic origin only |
| SharedDev | Origins.lsx | 16+ | Hirelings (all classes) |
| GustavDev | Origins.lsx | 6 | Astarion, Laezel, Gale, Shadowheart, Wyll, DarkUrge |
| GustavDev | OriginIntroEntities.lsx | — | Intro dialog/entity defs (different region) |
| Gustav | Origins.lsx | 6+ | Post-game recruitable companions |

## Region Structure

```xml
<region id="Origins">
  <node id="root">
    <children>
      <node id="Origin"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| Origin | [Origin.md](Origin.md) | Character origin: companion, hireling, or generic player |

## Cross-Region References

| Target Region | Via | Purpose |
|---------------|-----|---------|
| [Races](../Races/_REGION.md) | `RaceUUID` / `SubRaceUUID` | Origin's default race |
| [ClassDescriptions](../ClassDescriptions/_REGION.md) | `ClassUUID` / `SubClassUUID` | Origin's default class |
| [Backgrounds](../Backgrounds/_REGION.md) | `BackgroundUUID` | Origin's default background |
| [Gods](../Gods/_REGION.md) | `GodUUID` | Patron deity (clerics) |
| [Voices](../Voices/_REGION.md) | `VoiceTableUUID` | Voice actor assignment |
| [Tags](../Tags/_REGION.md) | `AppearanceTags.Object` / `ReallyTags.Object` | Tag classifications |

## Caveats

- **Split across sources**: Generic origin in Shared, hirelings in SharedDev, named companions in GustavDev/Gustav.
- **OriginIntroEntities.lsx** is in GustavDev but uses a **different region** — not `Origins`.
- **AvailableInCharacterCreation** has 3 values: `0` (hidden), `1` (playable), `2` (hireling) — not a bool.
