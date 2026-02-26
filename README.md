# korea-tourapi-skill

Agent skill for Korea Tourism Organization TourAPI (`KorService2`).

## Install with npx skills

From GitHub repo:

```bash
npx skills add <owner>/korea-tourapi-skill --skill korea-tourapi -g -a opencode
```

Install for all supported agents:

```bash
npx skills add <owner>/korea-tourapi-skill --skill korea-tourapi --agent '*' -g
```

List available skills in this repo:

```bash
npx skills add <owner>/korea-tourapi-skill --list
```

## Skill Focus

- Endpoint selection and parameter validation.
- Request/response schema validation with endpoint-level rules.
- Request construction for list/detail/code/sync calls.
- Pagination and error classification.
- Safe response normalization and model mapping.

## API Manual

This skill was authored from TourAPI 4.0 manual Ver 4.3 (2025-05-12).

## Included References

- `references/quick-reference.md`
- `references/wherewego-mapping.md`
- `docs/FEATURE_PLAN.md`
