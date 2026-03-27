# ObjectCategoriesItemComboPreviewData.txt

> **Path**: `Stats/Generated/ObjectCategoriesItemComboPreviewData.txt`
> **Format**: `new CraftingPreviewData` entries
> **Packs**: Shared (under SharedDev public) only

## Purpose

Defines UI preview data for crafting categories. Each entry provides an icon and tooltip for an `ObjectCategory` value used in `ItemCombos.txt`, allowing the crafting UI to display meaningful previews.

## Format

```
new CraftingPreviewData "NAME"
type "ObjectCategories"
data "Category" "CATEGORY_NAME"
data "Icon" "ICON_NAME"
data "Tooltip" "LOCALIZATION_HANDLE"
```

## Fields

| Field | Type | Notes |
|-------|------|-------|
| `Category` | String | Must match an `ObjectCategory` value from item stats |
| `Icon` | String | Icon resource name (often `"unknown"` for alchemy) |
| `Tooltip` | Localization handle | `handle:version` format |

## Example

```
new CraftingPreviewData "ALCH_Affinity_Air"
type "ObjectCategories"
data "Category" "ALCH_Affinity_Air"
data "Icon" "unknown"
data "Tooltip" "h5a9bf976g47e6g4e51ga980g8c1ca41b61a6;2"

new CraftingPreviewData "ConstructPart"
type "ObjectCategories"
data "Category" "ConstructPart"
data "Icon" "unknown"
data "Tooltip" "..."
```

## Notes

- Most entries use `"unknown"` as the icon, suggesting the UI falls back to the item's own icon
- Categories primarily cover alchemy affinities (`ALCH_Affinity_*`) and quest item groups
- The `type "ObjectCategories"` line is always present and always the same value
