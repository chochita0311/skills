---
name: project-context-sync
description: Keep local project context synchronized across sessions and repositories. Use when work spans one or multiple repos, when repeated re-explanations slow progress, or when code changes require context and optional ticket docs to stay aligned.
---

# Project Context Sync

Use this skill to keep work context accurate and reusable across sessions.

This skill applies to both:
- multi-repo work in one local project root
- single-repo work where long-running tasks need durable handoff notes

## Core Goal

Preserve momentum by reducing three recurring costs:
- search cost: re-finding files and modules
- re-explanation cost: repeating known facts each session
- drift cost: stale context that no longer matches code

## Scope Model

Always model context at two levels:
- `project root`: local workspace boundary, for example `<project-root>`
- `current repo`: actively edited repository inside the root

Optionally add:
- `related repos`: producer, consumer, scheduler, downstream, interface readers

## Source Priority

Use sources in this order.

1. Local shared context doc
- `inter-context.md` or `working-context.md`
- read first and treat as session baseline

2. Current repo code
- verify implementation state and detect context drift

3. Related repo code
- confirm cross-repo data flow, ownership, and compatibility

4. External source (optional)
- Jira, Confluence, issue tracker, internal wiki
- only when policy/source-of-truth recheck is needed

External tools are optional, not mandatory entry points.

## When to Use External Sources

Use ticket/wiki sources only when needed, such as:
- rollout, payload, schema, or policy is defined externally
- latest decision may have changed since last session
- ticket description must be updated to stay authoritative
- upcoming planned job/module exists only in ticket docs

Skip external rereads when:
- local context already captures stable facts
- implementation does not depend on changing external policy

## Optional Atlassian MCP Integration

Portability note:
- The core workflow of this skill is tool-agnostic.
- This section is Codex-specific and optional; skip it in environments without Codex MCP.

When Jira/Confluence recheck is needed and MCP is available, Atlassian MCP can be used as an optional source.
Do not make it a mandatory first step for every session.

Codex MCP integration file:
`~/.codex/config.toml`

Example configuration snippet:

```toml
[mcp_servers.atlassian]
url = "https://mcp.atlassian.com/v1/mcp"
```

Usage rule:
- use Atlassian MCP when ticket or policy freshness matters
- skip it when local context already has stable confirmed facts

## Required Context Fields

Maintain these fields in the shared context document.

1. `scope`
- `project root`
- `current repo`
- `related repos`

2. `work identity`
- ticket/story/task
- branch purpose
- current goal
- planned work not implemented yet (if ticket-defined)

3. `confirmed facts`
- proven architecture or policy facts
- cross-repo explanation if provided
- role mapping (producer/consumer/scheduler/downstream)

4. `open questions`
- unresolved decisions
- uncertain assumptions
- explicit recheck points

5. `working targets`
- files/classes/modules to open first
- grouped by project
- include `planned targets` when code does not exist yet

6. `recent decisions`
- naming decisions
- query/schema/index decisions
- payload contract decisions

7. `next handoff note`
- concise starter context for the next session

## Context Placement Patterns

Use one of these patterns.

Pattern A. Root shared context
- `<project-root>/inter-context.md`
- best when multiple repos share one active workflow

Pattern B. Repo-owned context
- `<project-root>/<repo-name>/inter-context.md`
- best when one repo is the context owner

Pattern C. Hybrid
- root-level overview + repo-specific context files
- use only when A or B is insufficient

## Propagation Workflow

For inter-repo work, follow this flow.

1. Create/update context in owner location
2. Record confirmed facts and working targets
3. In next repo/session, read owner context first
4. Add new facts and decisions back to the same context
5. Keep one canonical context per workflow to avoid divergence

## Session Startup Contract

At session start, provide at least:

```text
project root:
current repo:
current goal:
```

Recommended:

```text
project root:
current repo:
related repos:
shared context path:
confirmed facts:
current goal:
```

If following existing context:

```text
current repo:
follow context:
```

## Operating Procedure

Use this exact sequence unless a repository has stronger local rules.

1. Confirm `project root`, `current repo`, and active goal
2. Locate and read shared context doc
3. Open `working targets` first
4. Verify current repo implementation
5. Verify related repo behavior if cross-repo coupling exists
6. Use external source only if recheck is necessary
7. Update shared context with new confirmed facts and decisions
8. Write a short handoff note before ending session

## Stale Context Protocol

Treat context as synchronized state, not static notes.

Context is stale when any of these changes:
- query conditions
- payload fields
- message schema
- table/index/config shape
- module/class ownership
- inter-repo role boundaries

Protocol:
1. When code changes, update context in the same session
2. Mark obsolete assumptions clearly
3. Before next run, re-validate only high-risk assumptions

## Optional Ticket Sync

If requested or required, sync context updates back to tickets.

Typical cases:
- payload/query/schema in ticket is outdated
- ticket description is expected to be implementation reference
- planned job/module sections need to stay aligned with code plan

Recommended order:
1. code change
2. local context update
3. optional ticket description/comment update

## Context Lifecycle

Treat context as lifecycle-managed notes.

At job completion, either approach is valid based on user preference and reuse value:
- ephemeral memo mode: remove or archive the context once the job is done
- durable document mode: keep and expand the context when it is likely to be reused

Practical rule:
- low reuse value -> close and remove
- high reuse value -> normalize and keep as a maintained document

## Guardrails

Do:
- keep one canonical context file per workflow
- prioritize working targets to reduce search time
- distinguish confirmed facts vs open questions
- include planned targets when implementation does not exist yet

Do not:
- start every session by reading external tools automatically
- re-scan all related repos without a concrete reason
- keep stale assumptions after code contract changes
- maintain multiple conflicting context files for the same workflow

## Bundled Templates

- Use [templates/inter-context.md](templates/inter-context.md) to initialize or reset a context file.
- Use [templates/session-kickoff.txt](templates/session-kickoff.txt) as a reusable session input block.

