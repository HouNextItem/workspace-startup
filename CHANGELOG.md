# Changelog

## 1.1.0

- Added a machine-level workspace binding note without publishing the actual local path in the public repository.
- Preserved the generic discovery flow for other users while giving this machine a recorded default meaning for "Workspace" in local notes.
- Clarified that confirmed workspace roots should be reused instead of falling back to the current chat or checkout directory.

## 1.0.1

- Removed the personal machine-specific Workspace path from the skill instructions.
- Kept the discovery flow path-agnostic unless the user or existing Workspace notes provide a root.
- Clarified that the skill should not hardcode a private Workspace location.

## 1.0.0

- Generalized the skill into a reusable Workspace discovery and initialization flow.
- Kept `Agents.md` as the stable entry point for shared Workspace rules.
- Added explicit guidance for English-only filenames and `Project_###_ProjectName` folders.
- Clarified the user-facing behavior for creating or locating a Workspace and project folder.
