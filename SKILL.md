---
name: workspace-startup
description: Initialize, discover, and enforce a reusable project Workspace before starting project work. Use when the user says to run the Workspace startup skill, mentions $workspace-startup, wants to create or use a Workspace folder, starts a new project, asks to create Project-number-project-name folders, or wants Codex to follow Agents.md, global workbench, pitfall log, new-project SOP, or memory-center rules.
---

# Workspace Startup

Use this skill as the first step before project work that should live inside a persistent Workspace.

## Core Rule

Do not assume a fixed machine-specific Workspace path. Discover it from the user, an existing `Agents.md`, or the current project context. If the Workspace is missing, ask for confirmation before creating it.

## Startup Flow

1. Determine the Workspace root:
   - If the user provides a path, use that path.
   - Else if the current folder or an obvious parent contains `Agents.md` plus global Workspace documents, use that folder.
   - Else ask the user for the Workspace root path.
2. If the Workspace root does not exist, ask whether to create it.
3. Check for `Agents.md` in the Workspace root.
4. If `Agents.md` exists, read it first and follow the global document list inside it.
5. If `Agents.md` is missing, ask whether to initialize the standard global documents.
6. After reading or initializing the required global documents, explicitly confirm that the Workspace global documents have been read or created.
7. State the project folder that will be used or created before doing project work.

## Standard Global Documents

When the user asks to initialize a new Workspace, create these files in the Workspace root:

- `Agents.md`
- `Global_Workbench.md` or a localized equivalent such as `global-workbench` in the user's language
- `Compound_Learning_and_Pitfalls_Log.md` or a localized equivalent
- `New_Project_SOP.md` or a localized equivalent

Prefer localized names if the user already uses a language-specific naming style. Keep `Agents.md` exact because it is the stable entry point.

## Minimum Agents.md Contract

When initializing `Agents.md`, include a highest-priority rule that says:

- Before any project work, read `Agents.md` first.
- Then read the global workbench, compound-learning/pitfall log, and new-project SOP named by `Agents.md`.
- Confirm completion before starting work.
- Create each new project in its own `Project_###_ProjectName` folder or the localized equivalent chosen by the user.
- Keep final deliverables, scripts, intermediate files, raw materials, and references in the project subfolders defined by the SOP.

## New Project Flow

1. Inspect existing folders matching `Project_*` under the Workspace root.
2. Choose the next three-digit project number unless the global SOP says otherwise.
3. Create a new folder named `Project_###_ProjectName` or the localized equivalent.
4. Create the standard project structure from the global SOP.
5. Do not scatter project files in the Workspace root.
6. Put final deliverables in the project's output folder.
7. At task end, report files created or modified and update project/global logs when there is a useful lesson.

## Access and Safety

If filesystem access is blocked by sandboxing, request approval for the specific Workspace path. Do not silently fall back to another location.

If required documents are missing, tell the user which documents are missing and initialize them only after user approval or clear instruction.