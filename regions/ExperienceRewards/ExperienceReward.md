# Node: `ExperienceReward`

> **Region**: [ExperienceRewards](_REGION.md)
> **Folder**: `Levelmaps/`

---

## Attributes

> 22 nodes in Shared (vanilla)

| Attribute | Type | Count | Examples | Notes |
|-----------|------|-------|----------|-------|
| `UUID` | guid | 22/22 | `40806669-8c6b-4068-8bc4-07e4981bb020` | Primary key |
| `Name` | FixedString | 22/22 | `Zero`, `Civilian`, `Pack` | Reward tier name |
| `RewardType` | uint8 | 22/22 | `0` | Reward type category |
| `Level1` | uint32 | 22/22 | `0`, `1`, `3` | XP reward at character level 1 |
| `Level2` | uint32 | 22/22 | `0`, `1`, `5` | XP reward at character level 2 |
| `Level3` | uint32 | 22/22 | `0`, `1`, `10` | XP reward at character level 3 |
| `Level4` | uint32 | 22/22 | `0`, `1`, `20` | XP reward at character level 4 |
| `Level5` | uint32 | 22/22 | `0`, `1`, `40` | XP reward at character level 5 |
| `Level6` | uint32 | 2/22 | `0`, `1` | XP reward at character level 6 |
| `Level7` | uint32 | 2/22 | `0`, `1` | XP reward at character level 7 |
| `Level8` | uint32 | 2/22 | `0`, `1` | XP reward at character level 8 |
| `Level9` | uint32 | 2/22 | `0`, `1` | XP reward at character level 9 |
| `Level10` | uint32 | 2/22 | `0`, `1` | XP reward at character level 10 |
| `LevelSource` | uint8 | 5/22 | `1` | Level source reference |

## Cross-References

| From | To | Via |
|------|----|-----|
| ExperienceReward.UUID | [BackgroundGoal](../BackgroundGoals/BackgroundGoal.md) | BackgroundGoal.ExperienceReward |

## Caveats & Gotchas

- XP scales by character level — same reward name gives different XP at different levels.
- Most entries only define Levels 1–5 (BG3 Act 1); Levels 6–10 are sparse.
- Lives in `Levelmaps/` folder alongside LevelMapValues, despite being a different region.

## Cross-References

| From | To | Via |
|------|----|-----|
| — | — | — |

## Caveats & Gotchas

*(To be documented)*

## Similarities to Other Nodes

*(To be documented)*
