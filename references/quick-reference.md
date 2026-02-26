# KorService2 Quick Reference

Base: `https://apis.data.go.kr/B551011/KorService2`

Required baseline params for all endpoints:
- `serviceKey`
- `MobileOS`
- `MobileApp`
- `_type=json` (recommended)

## Endpoints

- `areaCode2`: area/sigungu codes
- `categoryCode2`: category hierarchy by content type
- `areaBasedList2`: area-based list
- `locationBasedList2`: coordinate-based list (requires `mapX`, `mapY`, `radius<=20000`)
- `searchKeyword2`: keyword list (requires `keyword`)
- `searchFestival2`: festival list (requires `eventStartDate`)
- `searchStay2`: stay list
- `detailCommon2`: common detail (requires `contentId`)
- `detailIntro2`: intro detail (requires `contentId`, `contentTypeId`)
- `detailInfo2`: repeated detail (requires `contentId`, `contentTypeId`)
- `detailImage2`: image detail (requires `contentId`)
- `areaBasedSyncList2`: sync list
- `detailPetTour2`: pet travel detail
- `ldongCode2`: legal-dong code lookup
- `lclsSystmCode2`: classification-system code lookup

## Dependency Rules

- `sigunguCode` requires `areaCode`
- `cat2` requires `cat1`
- `cat3` requires `cat1` + `cat2`
- `lDongSignguCd` requires `lDongRegnCd`
- `lclsSystm2` requires `lclsSystm1`
- `lclsSystm3` requires `lclsSystm1` + `lclsSystm2`

## Removed Legacy Params (Do Not Send)

- `detailCommon2`: `defaultYN`, `firstImageYN`, `areacodeYN`, `catcodeYN`, `addrinfoYN`, `mapinfoYN`, `overviewYN`
- `detailImage2`: `subImageYN`

For `detailCommon2`, use only:
- baseline params + `contentId`
- optional `numOfRows`, `pageNo`

## Common Result Fields

Header:
- `resultCode`, `resultMsg`

Body:
- `numOfRows`, `pageNo`, `totalCount`, `items.item`
