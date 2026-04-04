# Layer Model

Use this model to assign documentation responsibility.

## Entrance Layer
- Purpose: help the reader enter the repo correctly.
- Typical file: `AGENTS.md`
- Should contain: scope, codebase map, source-of-truth pointers, top-level rules.
- Should not contain: deep implementation detail, design specs, repeated setup commands, catch-all notes.

## Overview Layer
- Purpose: explain what the repository is and how to use it.
- Typical file: `README.md`
- Should contain: concise overview, local usage, navigation to deeper docs.
- Should not contain: detailed project policy or duplicated architecture guidance.

## Project Layer
- Purpose: hold durable project-specific detail.
- Typical files: policy, architecture, development, roadmap, package guide, or other role-specific docs
- Should contain: one owned responsibility per file.
- Should not contain: broad mixed-purpose summaries that overlap several layers at once.

## Specialized Layer
- Purpose: hold deeper domain-specific material.
- Examples: design docs, refactor plans, operations notes, package-specific guidance, domain references.
- Move information here when it becomes too detailed or too local for upper layers.
- Package-specific guidance can live near the owning package or subsystem when that placement improves clarity.

## Directory Rule
- Prefer adapting to the repository's existing clear structure over imposing a new one.
- If no good structure exists, create the smallest clear hierarchy that separates ownership cleanly.
- Choose folders and filenames based on ownership clarity, navigability, and maintainability.

## Ownership Rule
- Generalizable guidance moves upward.
- Package-specific or tightly local guidance moves downward.
- If two docs contain the same instruction, choose one owner and make the other doc point to it.
