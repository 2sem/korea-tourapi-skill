# KorService2 Request/Response Validation Matrix

Use this matrix before sending requests and after parsing responses.

## Request Validation

Baseline (all endpoints):
- `serviceKey`, `MobileOS`, `MobileApp`, `_type`

Endpoint required params:

- `areaCode2`: none beyond baseline
- `categoryCode2`: none beyond baseline
- `areaBasedList2`: none beyond baseline
- `locationBasedList2`: `mapX`, `mapY`, `radius` (`<=20000`)
- `searchKeyword2`: `keyword`
- `searchFestival2`: `eventStartDate`
- `searchStay2`: none beyond baseline
- `detailCommon2`: `contentId`
- `detailIntro2`: `contentId`, `contentTypeId`
- `detailInfo2`: `contentId`, `contentTypeId`
- `detailImage2`: `contentId`
- `areaBasedSyncList2`: none beyond baseline
- `detailPetTour2`: none beyond baseline (`contentid` optional)
- `ldongCode2`: none beyond baseline
- `lclsSystmCode2`: none beyond baseline

Dependency rules:
- `sigunguCode` -> requires `areaCode`
- `cat2` -> requires `cat1`
- `cat3` -> requires `cat1`, `cat2`
- `lDongSignguCd` -> requires `lDongRegnCd`
- `lclsSystm2` -> requires `lclsSystm1`
- `lclsSystm3` -> requires `lclsSystm1`, `lclsSystm2`

Removed params denylist (must never be sent):
- `defaultYN`, `firstImageYN`, `areacodeYN`, `catcodeYN`, `addrinfoYN`, `mapinfoYN`, `overviewYN`, `subImageYN`

## Response Validation

Success rule:
- `resultCode == "0000"`

Supported response shapes:

1. Standard envelope
- `response.header.resultCode`
- `response.header.resultMsg`
- `response.body.items.item`

2. Provider error payload
- top-level `resultCode`
- top-level `resultMsg`

Pagination checks (if list-like):
- `pageNo`, `numOfRows`, `totalCount` exist and are parseable

Endpoint minimum fields (item-level):

- List endpoints (`areaBasedList2`, `locationBasedList2`, `searchKeyword2`, `searchFestival2`, `searchStay2`, `areaBasedSyncList2`):
  - `contentid`, `contenttypeid`, `title`
- `detailCommon2`:
  - `contentid`, `contenttypeid`
- `detailIntro2`:
  - `contentid`, `contenttypeid`
- `detailInfo2`:
  - `contentid`, `contenttypeid`
- `detailImage2`:
  - `contentid`, `originimgurl` (or `smallimageurl`)
- Code endpoints (`areaCode2`, `categoryCode2`, `ldongCode2`, `lclsSystmCode2`):
  - code/name pair or documented list fields

Fallback rules:
- If required endpoint fields are missing, return parse warning + raw payload excerpt.
- If `items.item` is object, normalize to one-element array.
