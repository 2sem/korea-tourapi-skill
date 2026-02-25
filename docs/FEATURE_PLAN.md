# Feature Plan

## Recommended Feature Set: 10 features

1. Endpoint recommender by user intent.
2. Required-parameter validator (including dependency checks).
3. Canonical request builder with `_type=json` defaults.
4. Pagination planner (`pageNo`, `numOfRows`, `totalCount`).
5. Error classifier (HTTP vs OpenAPI vs provider resultCode).
6. List-response normalizer (single item vs array).
7. Detail-chain orchestrator (`detailCommon2` + intro/info/image).
8. Taxonomy/code lookup flow (`areaCode2`, `categoryCode2`, `ldongCode2`, `lclsSystmCode2`).
9. Sync-mode integration flow (`areaBasedSyncList2`, showflag/modifiedtime/oldContentid).
10. WhereWeGo model mapping playbook (`contentid`, `contenttypeid`, `mapx`, `mapy`, images).

## Suggested Delivery Phases

- Phase 1 (MVP): features 1-5
- Phase 2: features 6-8
- Phase 3: features 9-10

## Acceptance Criteria

- Skill always emits endpoint + validated params before implementation guidance.
- Skill catches all documented dependency-param rules.
- Skill provides safe parse notes for string-encoded numeric fields.
- Skill includes at least one list flow and one detail flow template.
