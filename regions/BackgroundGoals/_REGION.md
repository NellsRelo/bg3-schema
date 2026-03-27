# Region: `BackgroundGoals`

> **Folder**: `Backgrounds/`
> **Primary Node**: [BackgroundGoal](BackgroundGoal.md)
>
> 120+ inspiration goals (Gustav only)

---

## File Inventory

| Source | File | Entries | Version |
|--------|------|---------|---------|
| GustavDev | BackgroundGoals.lsx | 120+ | — |
| Gustav | BackgroundGoals.lsx | 120+ | — |

> **Gustav-only region.** Not present in Shared/SharedDev.

## Region Structure

```xml
<region id="BackgroundGoals">
  <node id="root">
    <children>
      <node id="BackgroundGoal"> ... </node>
    </children>
  </node>
</region>
```

## Node Types

| Node | File | Description |
|------|------|-------------|
| BackgroundGoal | [BackgroundGoal.md](BackgroundGoal.md) | Inspiration goal: background link, reward, XP |

## Cross-Region References

| Target Region | Via | Purpose |
|---------------|-----|---------|
| [Backgrounds](../Backgrounds/_REGION.md) | `BackgroundGoal.BackgroundUUID` → `Background.UUID` | Parent background |
| [ExperienceRewards](../ExperienceRewards/_REGION.md) | `BackgroundGoal.ExperienceReward` | XP reward entry |

## Caveats

- **Folder ≠ Region**: Lives in `Backgrounds/` folder but uses `BackgroundGoals` region.
- **Gustav-only** — Campaign-specific content, not in Shared.
