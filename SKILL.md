---
name: workspace-startup
description: Discover or initialize a reusable project Workspace before starting project work. Use when the user mentions $workspace-startup, asks to create or use a Workspace folder, wants a new project scaffold, or wants Codex to follow Agents.md, the global workbench, the pitfall log, or the new-project SOP.
---

# Workspace Startup

Use this skill first for project work that should live inside a persistent Workspace.

## Core Rule

Do not assume a fixed Workspace path. Discover it from the user, an existing `Agents.md`, or the current project context. If no Workspace can be found, ask before creating one.

## Workspace Discovery

1. If the user provides a Workspace path, use it.
2. Else if this skill or the Workspace documents already establish a known Workspace root for this machine, reuse that exact root.
3. Else if a Workspace root has already been established in the conversation, Workspace documents, or project notes, reuse that exact root.
4. Else look for `Agents.md` plus the global Workspace documents in the current folder or an obvious parent.
5. Else ask the user for the Workspace root path.

## Initialization Flow

If the Workspace root does not exist, ask whether to create it.

If the Workspace exists but `Agents.md` is missing, ask whether to initialize the standard global documents.

When the user asks to initialize a new Workspace, create these files in the Workspace root:

- `Agents.md`
- `Global_Workbench.md`
- `Compound_Learning_and_Pitfalls_Log.md`
- `New_Project_SOP.md`

Prefer English filenames in the shared Workspace. Prefer names without spaces. Use underscores or hyphens so PowerShell and CLI tools do not split paths unexpectedly.
Prefer English directory names for the shared Workspace root and for all project folders.
Do not hardcode a personal or machine-specific Workspace path into this skill.
Do not reinterpret the current chat folder or the current project checkout as the Workspace root when a Workspace root has already been established.

## Machine Workspace Note

When this skill is used on the machine where the Workspace root has already been established, treat the locally recorded Workspace root as the default meaning of "Workspace" unless the user explicitly gives another path.
After a Workspace is created or confirmed on this machine, record the path in the Workspace documents so future sessions can reuse it.

## Required `Agents.md` Contract

When creating or updating `Agents.md`, include a highest-priority rule that says:

- Read `Agents.md` before any project work.
- Then read the global workbench, the pitfall log, and the new-project SOP named by `Agents.md`.
- Confirm completion before starting project work.
- Create each new project in its own `Project_###_ProjectName` folder.
- Keep final deliverables, scripts, intermediate files, raw materials, and references inside the project subfolders defined by the SOP.

## New Project Flow

1. Inspect existing `Project_*` folders under the Workspace root.
2. Choose the next three-digit project number unless the SOP says otherwise.
3. Create a new `Project_###_ProjectName` folder.
4. Create the standard project subfolders from the SOP.
5. Do not scatter project files in the Workspace root.
6. Put final deliverables in the project output folder.
7. At task end, report the files created or modified and update the project or global logs when there is a useful lesson.

## User Communication

- Tell the user which Workspace root was found or created.
- If you create the Workspace, say so clearly.
- If the Workspace folder does not exist yet, ask whether Codex should create it or whether the user will create it manually.
- If you create a project folder, tell the user the folder name.
- If required documents are missing, say which ones are missing and ask before initializing them.

## Safety

If filesystem access is blocked by sandboxing, request approval for the specific Workspace path. Do not silently fall back to another location.
