# Node: `SpeakerGroup`

> **Region**: [SpeakerGroups](_REGION.md)
> **Folder**: `Voice/`
> **Source**: `Gustav/Public/Gustav/Voice/SpeakerGroups.lsx`, `Gustav/Public/GustavDev/Voice/SpeakerGroups.lsx`, `Shared/Public/Shared/Voice/SpeakerGroups.lsx`
> **Total Nodes**: ~267 combined (Gustav: 68, Gustav/GustavDev: 156, Shared: 43)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | LSString | always | `01305de8-4f86-0e98-7778-710bc022b1d7` | Primary key (note: LSString, not guid!) |
| `Name` | LSString | always | `GROUP_TestLevel_Heads`, `GROUP_Daisy_Female`, `GROUP_WLD_Priests` | Internal name; GROUP_ prefix convention |
| `Description` | LSString | always | `Used in TestLevel_Heads to test face fx...`, `Daisy female dummy` | Developer description of group purpose |
| `OverwriteSpeakerUuid` | LSString | ~120/267 | `c6ae64e6-87de-4faf-af36-33f0ab222431` | UUID to override speaker identity (optional) |

## Child Nodes

None.

## Patterns of Use

- Groups speakers (NPCs) for dialogue/voice line assignment
- `Name` uses `GROUP_` prefix + area/act abbreviation: `GROUP_GLO_Myrkul`, `GROUP_SHA_Necromancer_Skeletons`, `GROUP_Act3_LOW_WaterQueensHouse_Waveservants`
- `OverwriteSpeakerUuid` present on ~45% of entries — allows redirecting voice to a different character template
- Multi-pack: Gustav has general groups, Gustav/GustavDev has act-specific groups, Shared has system-wide groups
- Shared includes meta-groups like `GROUP_Constructs`, `GROUP_PartyMembers`, `GROUP_Signs`

## Caveats & Gotchas

- **UUID type is LSString, not guid** — unusual for a primary key
- `Description` is a developer note, not player-facing text
- `OverwriteSpeakerUuid` is also LSString despite holding a UUID value

## Similarities to Other Nodes

Related to `Voice` region (which defines individual voice profiles).
