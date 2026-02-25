# kto-tourapi-korservice2-skill

Agent skill for Korea Tourism Organization TourAPI 4.0 (`KorService2`).

## Install with npx skills

From GitHub repo:

```bash
npx skills add <owner>/kto-tourapi-korservice2-skill --skill kto-tourapi-korservice2 -g -a opencode
```

Install for all supported agents:

```bash
npx skills add <owner>/kto-tourapi-korservice2-skill --skill kto-tourapi-korservice2 --agent '*' -g
```

List available skills in this repo:

```bash
npx skills add <owner>/kto-tourapi-korservice2-skill --list
```

## Skill Focus

- Endpoint selection and parameter validation.
- Request construction for list/detail/code/sync calls.
- Pagination and error classification.
- Safe response normalization and model mapping.

## API Manual

This skill was authored from TourAPI 4.0 manual Ver 4.3 (2025-05-12).

## Included References

- `references/quick-reference.md`
- `references/wherewego-mapping.md`
- `docs/FEATURE_PLAN.md`
