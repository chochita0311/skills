# Example Output

Use this as a shape reference for a full `docs-structuring` pass.

This is an example of the reporting format, not a mandatory literal template.

## Operating Mode Used
- `incremental`

## Doc-Role Map
| File | Role | Owner Level | Current Problems | Planned Action |
| --- | --- | --- | --- | --- |
| `AGENTS.md` | entrance | entrance | duplicates setup summary from `README.md` | tighten and keep as contributor entrance |
| `CLAUDE.md` | entrance | entrance | duplicates `AGENTS.md` too closely | align as parallel AI entrance file |
| `README.md` | overview | overview | duplicates setup and project summary from deeper docs | keep user-facing overview and own setup |
| `docs/handbook.md` | mixed-purpose | mixed | mixes policy, architecture, setup, roadmap, and package-local guidance | split ownership and re-home content |
| `packages/payments/README.md` | specialized reference | package | already owns local package flags clearly | keep in place and link from overview docs if needed |

## Ownership Changes
- `README.md` becomes the owner of local run instructions.
- `AGENTS.md` and `CLAUDE.md` become entrance-layer files only.
- `docs/handbook.md` stops being the owner of setup and package-local guidance.
- `packages/payments/README.md` remains the owner of payments-specific flags.

## Before -> After Structure Summary
- Before:
  - duplicated setup instructions across entrance docs, overview doc, and handbook
  - one mixed-purpose handbook file owned too many responsibilities
  - package-local guidance was duplicated in both central docs and package docs
- After:
  - entrance files route to owned docs
  - `README.md` owns overview and setup
  - central durable docs own policy, architecture, and roadmap
  - package-local guidance stays near the package owner

## Moved Content Summary
- local run steps moved from `AGENTS.md`, `CLAUDE.md`, and `docs/handbook.md` into `README.md`
- payments environment flag guidance removed from `docs/handbook.md` and left in `packages/payments/README.md`
- handbook policy and architecture sections re-homed into owned docs

## Removed Duplication Summary
- removed repeated repository description from `AGENTS.md`, `CLAUDE.md`, and `README.md`
- removed repeated local run command from four files down to one owner
- removed repeated payments package flag notes from central and local docs

## Cross-Link Additions
- `AGENTS.md` -> `README.md` for overview and setup
- `CLAUDE.md` -> `README.md` and `AGENTS.md`
- `README.md` -> policy, architecture, and roadmap docs
- central project docs -> `packages/payments/README.md` only when package-local context is needed

## Suggested-Only Restructures
- consider splitting `docs/handbook.md` into separate policy, architecture, and roadmap docs if the repository keeps growing
- consider adding a docs index if more specialized doc areas appear later

## Decision Confidence Summary
- `high`
  - keep setup owned by `README.md`
  - keep package-local flags owned by `packages/payments/README.md`
  - align `AGENTS.md` and `CLAUDE.md` as entrance-layer docs
- `medium`
  - split `docs/handbook.md` into several docs if growth continues
- `low`
  - whether a separate docs index is needed immediately

## Unresolved Or Low-Confidence Items
- whether the repository needs a separate roadmap file yet
- whether `CLAUDE.md` should remain distinct in tone or mirror `AGENTS.md` more closely
