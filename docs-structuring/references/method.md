# Method

Use this file for the full document-structuring procedure.

## Purpose
- audit the current documentation set
- classify ownership and layering
- reorganize without discarding useful content
- reduce duplication
- leave a maintainable doc tree behind

## Working Sequence

### 1. Audit the active docs
- Start from the root and the most central entry docs.
- Read enough of the current structure to understand:
  - what the repo is
  - where users start
  - where contributors start
  - where durable detail currently lives
- Respect user exclusions for protected, legacy, or deferred doc areas.

### 2. Classify document roles
- Assign each active doc one primary role where possible:
  - entrance
  - overview
  - policy
  - architecture
  - development
  - roadmap
  - specialized reference
  - tracking or logs
- If a file cannot be summarized in one short ownership statement, treat it as mixed-purpose.

### 3. Detect contract failures
- Look for:
  - duplicated setup steps
  - duplicated repository descriptions
  - repeated rules across layers
  - vague catch-all summary docs
  - entrance docs carrying deep implementation detail
  - missing cross-links that make context hard to follow
  - multiple AI entrance docs drifting apart

### 4. Choose the owning layer
- Move generalizable guidance upward.
- Move package-specific, feature-specific, or tightly local guidance downward.
- Keep one durable owner for each recurring fact or rule.
- Preserve useful preexisting content by relocating or merging it into the right owner.
- When guidance is tightly local to one package, module, or subsystem, prefer placing it near that owner instead of centralizing it artificially.

## Entrance-Doc Handling

### Single entrance doc
- Keep it short and map-like.
- It should point to deeper docs rather than reteach them.

### Multiple AI entrance docs
- When `AGENTS.md`, `CLAUDE.md`, or similar files coexist, align them before editing them independently.
- Keep their ownership model coherent:
  - entrance files route
  - deeper docs own detail
- Do not casually let separate AI entry docs accumulate different versions of the same durable guidance.
- Check whether overview docs or documentation maps should also be updated so the entrance layer is discoverable as a set rather than through one outdated pointer.

## Restructure Boundaries

### Apply directly
- removing clear duplication
- rewriting for ownership clarity
- tightening entrance docs
- adding useful cross-links
- re-homing existing useful content

### Suggest first, then wait for approval
- splitting one doc into several new docs when that split is helpful but optional
- introducing a broader new folder hierarchy
- larger reorganizations that materially change navigation patterns

## Writing Standard
- Keep each file clean and readable.
- Make each file descriptively clear about why it exists.
- Prefer linked layers over repeated prose.
- Keep filenames and placement aligned with ownership and navigability.

## Finish Pass
- Check the result with [checklist.md](checklist.md).
- Confirm that the tree is cleaner and easier to maintain than before.
- If no comparable rerun exists yet, treat the refinement as improved but not fully rerun-validated.
