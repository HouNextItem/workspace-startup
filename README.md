# Workspace Startup

Workspace Startup helps Codex find or initialize a persistent project Workspace before work begins.

Repository: [HouNextItem/workspace-startup](https://github.com/HouNextItem/workspace-startup)

## What it does

- Finds an existing Workspace root
- Reads `Agents.md` and the global Workspace documents
- Creates the standard Workspace files when needed
- Recommends English filenames and `Project_###_ProjectName` folders

## Standard Workspace Files

- `Agents.md`
- `Global_Workbench.md`
- `Compound_Learning_and_Pitfalls_Log.md`
- `New_Project_SOP.md`

## Notes

- `Agents.md` is the stable entry point
- Prefer filenames without spaces
- Prefer English directory names for the Workspace root and project folders
- Tell the user when a Workspace is found or created
- Tell the user when a project folder is created
