---
name: init-design
description: Use when starting or resetting product design from a first screen artifact and you need to turn it into a stable design constitution with compatibility checks, reusable rules, and a concrete startup plan. Use for web, mobile, or mixed products when a visual starting point exists but should not become the system by itself.
---

# Init Design

Use this skill to turn a first screen artifact into a stable design starting point.

## Use This Skill When
- A project has a first screen, mockup, or AI-generated entry page but no stable design rules yet
- The visual direction exists, but compatibility, expandability, and maintainability are still unclear
- You need to convert a screen into:
  - design DNA
  - primitive tokens
  - semantic tokens
  - layout rules
  - core component rules
  - a design constitution
  - a startup plan
- A project has drifted and needs its design baseline rebuilt from the current artifact

## Do Not Use This Skill When
- There is no visual entry artifact yet
- The task is only to polish a single existing component
- The task is implementation-only and the design constitution already exists
- The task is a full visual redesign without a stable starting artifact to evaluate

## Invocation Examples
- `Use $init-design to analyze this project from the current first screen artifact and produce a design constitution plus startup plan.`
- `Use $init-design to review this initial screen and turn it into stable tokens, layout rules, and a startup plan.`
- `Use $init-design to reset the design baseline for this app using the current main screen and the existing product constraints.`

## Workflow
1. Read `references/method.md` for the full workflow.
2. Identify the starting artifact type:
   - `single-screen artifact`
   - `screen-plus-context`
3. Evaluate the artifact as design input, not as the final system.
4. Check compatibility against:
   - product goals
   - entities
   - roles
   - states
   - device priority
5. Write or update the constitution with `templates/design-constitution.md`.
6. Produce or update the current design startup plan with `templates/plan.md`.
7. Use `references/checklist.md` as the final quick validation pass.

## Package Layout
- `references/`
  - workflow and explanatory material to read while thinking
- `templates/`
  - reusable output scaffolds to copy or adapt for constitutions and startup plans
- `agents/openai.yaml`
  - optional UI metadata

## Output Location
- Write project outputs under split policy/plan folders by default:
  - `./docs/policies/design/design-constitution.md`
  - `./docs/plans/design/design-plan.md`
- Only use another folder if the project already has an established convention.

## Core Rule
- Start from a screen artifact, but never let that artifact become the system by itself.
- Always convert the artifact into explicit rules before expanding screens.
- Always validate design against compatibility, expandability, and maintainability constraints.
- Treat the constitution as the stable rule document.
- Treat the plan as the current working document.
- Keep screen families in the constitution only when they are durable product structure.
- Keep concrete build sequence, open questions, and immediate implementation scope in the plan.
- Defer logs unless repeated design iterations or handoffs make them necessary.

## Output Separation
- `design-constitution.md` answers:
  - what is locked
  - how the product should feel
  - which tokens, semantics, layouts, and component rules are durable
  - which screen families are fundamental to the product structure
- `design-constitution.md` must not include:
  - immediate next actions
  - implementation sequencing
  - file-by-file work items
  - temporary uncertainty that does not change durable rules
  - transitional wording such as `for now`, `until later`, or `currently unless changed`
- `design-plan.md` answers:
  - what is still unresolved
  - what should be built or clarified next
  - which screen scope is active now
  - which risks or constraints need follow-up
  - which decisions are still open
  - which build sequence is active now
  - what versioning or constitution delta this run introduced
- `design-plan.md` should refer to durable decisions briefly instead of restating them:
  - use short status or delta bullets when the constitution already captures the full rule
  - summarize locked decisions only enough to explain the active plan
- `design-plan.md` must not include:
  - a full restatement of the constitution
  - full token tables that are already locked
  - full component definitions that are already locked
  - durable rules unless they are being changed
  - stable product context copied in full when a short reference to the constitution is enough
