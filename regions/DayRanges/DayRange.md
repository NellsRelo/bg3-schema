# Node: `DayRange`

> **Region**: [DayRanges](_REGION.md)
> **Folder**: `Calendar/`
> **Source**: `Shared/Public/Shared/Calendar/DayRanges.lsx`
> **Total Nodes**: ~18 (Shared only)

---

## Attributes

| Attribute | Type | Frequency | Examples | Notes |
|-----------|------|-----------|----------|-------|
| `UUID` | guid | x18 | `2157cc08-f40b-4645-87d3-e7e3baf59190` | Primary key |
| `Name` | FixedString | x17 | `Hammer`, `Midwinter`, `Alturiak` | Forgotten Realms month/holiday name |
| `DisplayName` | TranslatedString | x18 | — | Localized display name |
| `DisplayCommonName` | TranslatedString | x18 | — | Common (real-world equivalent) name |
| `Start` | uint32 | x17 | `1`, `31`, `32` | Day-of-year start (1-indexed) |
| `End` | uint32 | x17 | `30`, `31`, `61` | Day-of-year end (inclusive) |
| `LeapYearStart` | uint32 | x8 | `214`, `215`, `245` | Adjusted start for leap years |
| `LeapYearEnd` | uint32 | x8 | `214`, `244`, `274` | Adjusted end for leap years |

## Child Nodes

None.

## Patterns of Use

- Defines the Harptos calendar used in the Forgotten Realms
- 12 months + festival/holiday entries (Midwinter, Greengrass, Midsummer, Highharvestide, Feast of the Moon)
- `Start`/`End` missing on 1 node (likely the special "Year" or aggregate entry with only UUID + DisplayName)
- `LeapYearStart`/`LeapYearEnd` only on 8 nodes — months affected by Shieldmeet leap day

## Caveats & Gotchas

- Not all nodes have `Name`/`Start`/`End` (1 omitted)
- Leap year fields are sparse — only present where the date range shifts

## Similarities to Other Nodes

None — unique calendar system.
