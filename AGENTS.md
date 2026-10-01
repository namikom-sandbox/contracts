# AGENTS.md

## Build and test
- Build: none; the contracts are YAML.
- Unit tests: none.
- Component or integration tests: none (needs Docker: no).
- Lint and format: `npm ci && npm run lint` (Redocly, `recommended` rules)
- CI workflow that runs these: `.github/workflows/ci.yml`

## Conventions
- One OpenAPI 3.1 file per service, in `openapi/`.
- Changes within a version are additive. A breaking change needs a new major version and a note to every consumer.
- Every operation has an `operationId`, a `summary` and its 4xx responses.

## Do not touch
- Paths the agent must not change without a person: `.github/workflows/`

## Owners
- Default reviewers and code-owner teams: `@namikom-sandbox/platform-team`; `openapi/orders.yaml` also `@namikom-sandbox/orders-team`
- Who answers product questions for this repo: the team that owns the service the file describes

## Known traps
- `orders-service` implements `openapi/orders.yaml` by hand, and `storefront` keeps a copy in `api/orders.yaml`. A change here isn't live until both are updated.
