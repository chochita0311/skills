# Init Design Checklist

## Purpose
- Use this as the quick execution sheet for `init-design`.
- This is the short version of the full guide.
- Run through it before expanding screens.

## 1. Identify The Start
- What is the current starting artifact?
  - first screen artifact
  - first screen plus product context
- Which starting point is this?
  - single-screen artifact
  - screen-plus-context

## 2. Confirm Product Reality
- Who are the primary users?
- What are the 3 main repeated tasks?
- Is the product read-heavy, action-heavy, or workflow-heavy?
- Which device matters first?

## 3. Check Compatibility
- What entities already exist?
- What roles already exist?
- What important states already exist?
- What validations or permissions will affect UI?
- What future expansion is already likely?

## 4. Evaluate The First Artifact
- Extract from the first screen:
  - what is the tone?
  - what is the content hierarchy?
  - what components repeat?
  - what is missing?
- Then validate against system constraints:
  - what screen families are implied?
  - what role differences are implied?
  - what UI states are required?

## 5. Lock Design DNA
- Write 5 to 8 tone keywords
- Write 3 to 5 visual principles
- Write 5 to 8 anti-principles

## 6. Lock Primitive Tokens
- Colors
- Typography
- Spacing
- Radius
- Shadows
- States

## 7. Lock Semantic Tokens
- Page background
- Surface hierarchy
- Text hierarchy
- Action hierarchy
- Feedback hierarchy
- Shell sizing
- Reading mode

## 8. Lock Layout Rules
- App shell
- Navigation model
- Breakpoints
- Mobile transformation
- Content width rule

## 9. Lock Core Components
- Button
- Input
- Card
- List row
- Table or grid
- Tabs or chips
- Dialog or drawer
- Empty/loading/error state

## 10. Define Screen Families
- Identify the minimum durable screen families implied by the product
- Typical early families:
  - entry or list
  - detail or read
  - create, edit, or action flow
- Do not force three if the product currently supports fewer
- Do not stop at three if the product clearly needs more
- Put durable families in the constitution
- Put current build order in the plan

## 11. Check Stability
- Can these screens be built without new colors?
- Can they be built without new radius values?
- Can they be built without page-specific hacks?
- Do backend states map to UI states?

## 12. Define Guardrails
- No raw values outside primitive tokens
- No direct primitive use in components when semantic aliases should exist
- No casual redesign-by-prompt
- No uncontrolled screen expansion before durable screen families are stable

## 13. Output Required
- Constitution contains the durable sections:
  - project context
  - compatibility constraints
  - design DNA
  - primitive tokens
  - semantic tokens
  - layout rules
  - core components
  - screen families
- Plan contains the active sections:
  - summary
  - starting artifact
  - active deltas or constitution status
  - what is not stable yet
  - active screen scope
  - current build sequence
  - open decisions
  - risks
  - next actions
  - versioning note when the constitution is created or changed

## 14. Check Separation
- Can the constitution stand on its own as the stable rule document?
- Can the plan be read as a current working document without repeating the whole constitution?
- If the plan is deleted, does the constitution still explain the design system?
- If the constitution needs weekly edits for short-term tasks, separation is too weak
- If the plan mentions locked decisions, are they reduced to short status or delta notes instead of rewritten rule sections?
- Even if the plan is compact, does it still keep the active planning spine instead of collapsing into summary plus next actions only?

## 15. Final Question
- If I stop this work for a month, will I know:
  - what the product is
  - how it should feel
  - which values are locked
  - which components already exist
  - what to build next
- If not, `init-design` is not finished yet.
