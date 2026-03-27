# Node: `DLC`

> **Region**: [DLC](_REGION.md)
> **Folder**: `DLC/`
> **Vanilla entries**: 4 (GustavDev; empty in Gustav)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | 4/4 | `43962845-...` | Primary key |
| `Name` | LSString | 4/4 | `DLC_Gustav_DigitalDeluxe`, `DLC_Gustav_LarianNetworkSignUp` | Internal DLC identifier |
| `GalaxyAPICode` | uint32 | 2/4 | `1157299235`, `1160386633` | GOG Galaxy store code |
| `SteamAPICode` | uint32 | 2/4 | `2378500`, `2378510` | Steam store app ID |
| `PS5APICode` | uint32 | 2/4 | `2`, `1` | PlayStation Store code |
| `XLiveAPICode` | uint32 | 1/4 | `2741026280` | Xbox Live code |
| `TwitchAPICode` | uint32 | 1/4 | `1000` | Twitch integration code |
| `UnlockType` | uint8 | 1/4 | `1` | How the DLC is unlocked (e.g., account signup) |

## Child Nodes

*(None in vanilla data)*

## Patterns of Use

- Most DLC entries have platform-specific API codes (Steam, GOG, PS5, Xbox).
- `DLC_Gustav_LarianNetworkSignUp` uses `UnlockType` instead of store codes.
- `DLC_Gustav_Twitch_Reward` only has `TwitchAPICode`.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

- Empty in Gustav pack; only GustavDev has entries.
- Platform API codes are optional — each DLC only has codes for its relevant platforms.

## Similarities to Other Nodes

*(None)*
