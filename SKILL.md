---
name: workspace-startup
description: Load and enforce the user's global Workspace operating rules before starting any project work. Use when the user says to run the Workspace startup skill, mentions $workspace-startup, starts a new project in E:\33546\project\Workspace, asks to create Project-number-project-name folders, or wants Codex to follow the global workbench, pitfall log, new project SOP, or Agents.md memory-center rules.
---

# Workspace Startup

Use this skill as the first step before doing any project work in the user's global Workspace.

## Workspace Root

```text
E:\33546\project\Workspace
```

## Required Startup Read

Before creating, editing, analyzing, or outputting project files under the Workspace:

1. Check that the Workspace root exists.
2. Read `E:\33546\project\Workspace\Agents.md` first.
3. Follow `Agents.md` exactly, including reading the global workbench, pitfall/compound-interest log, and new-project SOP documents named there.
4. After reading all required startup documents, explicitly confirm in Chinese that the Workspace global documents have been read.
5. State the project folder that will be used or created.

## Startup Procedure

1. If the user is starting a new project, inspect existing folders matching `Project_*` under the Workspace root and choose the next three-digit number.
2. Create the new project folder using the naming rule from the global SOP: `Project_###_ProjectName` or the Chinese equivalent specified by the global documents.
3. Create the standard project structure from the global SOP unless the existing global documents say otherwise.
4. Put final deliverables in the project's output folder.
5. Put scripts, intermediate files, raw materials, references, and review notes in the matching project subfolders required by the SOP.
6. Do not scatter project files in the Workspace root.
7. At task end, report the files created or modified and update project/global logs when there is a useful lesson.

## If Access Requires Approval

The Workspace root is outside the default Codex generated workspace. If filesystem access is blocked by sandboxing, request approval to read or write the specific Workspace path. Do not silently fall back to another location.

## If Documents Are Missing

If `Agents.md` or any required global document named inside it is missing, tell the user which document is missing and recreate it only after user approval or clear instruction. Do not invent a replacement silently.