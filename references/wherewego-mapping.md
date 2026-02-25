# WhereWeGo Mapping Notes

This mapping mirrors patterns used in the WhereWeGo iOS app data layer.

## Primary ID and Type

- `contentid` -> model `id` (Int)
- `contenttypeid` -> model `type` enum

## Text Fields

- `title` -> `title`
- `tel` -> `tel`
- `addr1` -> `primaryAddr`
- `addr2` -> `detailAddr`
- `overview` -> `overview` (`<br>` converted to newline)

## Coordinates and Distance

- `mapx` -> `longitude`
- `mapy` -> `latitude`
- `dist` -> distance from location query center

## Image and License

- `firstimage` -> image URL
- `firstimage2` -> thumbnail URL
- `cpyrhtDivCd` should be preserved for licensing behavior

## Date-like Fields

- `createdtime`, `modifiedtime` are string date-time values (`yyyyMMddHHmmss` style)
- Parse defensively; keep raw values if parse fails

## Implementation Guardrails

- TourAPI often returns numeric values as strings.
- Optional fields can be empty string; treat as null.
- Maintain pagination metadata with each fetch.
