# Node: `WeightCategory`

> **Region**: [WeightCategories](_REGION.md)
> **Folder**: `WeightCategories/`
> **Source**: `Shared/Public/Shared/WeightCategories/WeightCategories.lsx`
> **Total Nodes**: ~6 (Shared only)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x6 | `e3f0b9d4-8238-482e-9f07-1567b242d90e` | Primary key |
| `ObjectSize` | FixedString | x6 | `Tiny`, `Small`, `Medium` | D&D size category |
| `MaxWeight` | int32 | x6 | `6000`, `40000`, `200000` | Max weight in grams for this size category |

## Child Nodes

| Child | Count | Description |
|-------|-------|-------------|
| `Tags` | x6 | Tags associated with each weight category (one Tags group per node) |

## Patterns of Use

- Maps D&D creature/object size categories to maximum weight thresholds
- 6 categories covering standard size ranges: Tiny, Small, Medium, Large, Huge, Gargantuan
- Weights in grams (6000g = 6kg for Tiny, 200000g = 200kg for largest)
- Each weight category has associated `Tags` children for tagging items/objects

## Caveats & Gotchas

- Weights are in **grams**, not pounds or kg
- `Tags` children may contain multiple tag UUIDs per category

## Similarities to Other Nodes

None — unique weight/size classification system.
