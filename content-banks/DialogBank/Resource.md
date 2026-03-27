# Node: `Resource`

> **Region**: [DialogBank](_REGION.md)
> **Child Depth**: 2 (Resource → SpeakerSlotsWithLines)

---

## Node Hierarchy

```
Resource
└── SpeakerSlotsWithLines    ← repeated (speakers that have lines)
    └── HasLines (bool)
```

## Attributes

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `ID` | FixedString | UUID primary key | `ca90c53f-...` |
| `Name` | LSString | Dialog name | `CMB_AD_LookingForHiddenPlayer` |
| `SourceFile` | LSString | Dialog source file (.lsj) | `Mods/Shared/Story/Dialogs/.../X.lsj` |
| `EnableTimeline` | bool | Whether dialog uses timeline system | `True` |
| `automated` | bool | Automated (non-interactive) dialog | `True` |
| `isBehaviour` | bool | Behavior-triggered dialog | `False` |
| `isPrivateDialog` | bool | Private (non-overheard) dialog | `False` |
| `isSubbedDialog` | bool | Subtitle-only dialog (no VO) | `False` |
| `isWorld` | bool | World dialog (ambient) | `False` |
| `AllowDeadSpeakers` | bool | Allow dead NPCs as speakers | `False` |
| `BlockFTB` | bool | Block fast-travel during dialog | `False` |
| `IsAllowingJoinCombat` | bool | Allow joining combat during dialog | `False` |
| `_OriginalFileVersion_` | int64 | Engine version stamp | `144115207403209030` |

## Child: SpeakerSlotsWithLines

| Attribute | Type | Description | Example |
|-----------|------|-------------|---------|
| `HasLines` | bool | Whether this speaker slot has dialog lines | `True` |

## Cross-References

| From | To | Via |
|------|----|-----|
| Resource.ID | [TimelineBank](../TimelineBank/_REGION.md) | `DialogResourceId` |
| Resource.SourceFile | Dialog `.lsj` files | Actual dialog content |

## Caveats

- Several attributes use **lowercase camelCase** (`automated`, `isBehaviour`, `isWorld`) — legacy naming convention
