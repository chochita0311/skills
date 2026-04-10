---
name: init-serena
description: Initialize Serena for a project. Use when a user asks to run "init-serena" or wants to activate a project, check onboarding status, and load initial Serena instructions.
---

# Init Serena

## Workflow
1. Call `serena.activate_project` with the project name or path provided by the user (or `cwd` if not provided).
2. Call `serena.onboarding` and `serena.check_onboarding_performed` and note the result.
3. Call `serena.initial_instructions` to load the Serena toolbox instructions.
