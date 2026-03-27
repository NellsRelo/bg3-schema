# Node: `BackgroundGoal`

> **Region**: [BackgroundGoals](_REGION.md)
> **Folder**: `Backgrounds/`

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | always | — | Primary key |
| `BackgroundUUID` | guid | always | parent background reference | Links to Background.UUID |
| `Title` | TranslatedString | always | handle + version | Goal display title |
| `Description` | TranslatedString | always | handle + version | Goal description |
| `RewardLevel` | uint32 | always | `2`, `3`, `4` | Achievement tier |
| `InspirationPoints` | uint32 | always | `1` | Inspiration granted on completion |
| `ExperienceReward` | guid | always | XP reward UUID | Links to ExperienceRewards |

## Cross-References

| From | To | Via |
|------|----|-----|
| BackgroundGoal.BackgroundUUID | [Background](../Backgrounds/Background.md) | Background.UUID |
| BackgroundGoal.ExperienceReward | [ExperienceRewards](../ExperienceRewards/_REGION.md) | reward entry UUID |

## Caveats & Gotchas

- **Gustav-only** — Only exists in GustavDev/Gustav, not in Shared.
- **149 entries** in Gustav (vanilla) — Multiple goals per background, tiered by RewardLevel.
- **Same folder, different region** — Lives in `Backgrounds/` folder but uses `BackgroundGoals` region.
