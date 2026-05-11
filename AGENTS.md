# Repository Guidelines

## Purpose

This repository is the parent organizer for my RNCP7-level portfolio work. It should stay lightweight: documentation, `.gitmodules`, rank/project folders, and submodule pointers belong here. Actual project source code should live in its own GitHub repository and be linked here as a submodule.

## Expected Workflow

When starting or adding a project:

1. Create the standalone project repository on GitHub first.
2. Add it to this repository as a submodule under the appropriate folder:

```sh
git submodule add <repo-url> projects/<project-name>
```

3. Update `README.md` with a short project description and a link to the submodule path.
4. Commit only the parent repository metadata changes: `.gitmodules`, the gitlink, and documentation.

Do not copy full project source code directly into this parent repo unless explicitly requested. Prefer submodules so each project keeps independent history, issues, and cloneability.

## Repository Layout

Current intended layout:

```text
42-RNCP7/
  README.md
  AGENTS.md
  .gitignore
  .gitmodules
  projects/
    project-name/
```

The layout may evolve as RNCP7 requirements become clearer, but keep naming consistent, lowercase where practical, and descriptive.

## Submodule Commands

Clone all projects:

```sh
git clone --recurse-submodules git@github.com:chocolate-brownie/42-RNCP7.git
```

Initialize after cloning:

```sh
git submodule update --init --recursive
```

Update a submodule pointer after work inside a project repo:

```sh
git submodule update --remote projects/<project-name>
git add projects/<project-name>
git commit -m "update <project-name> submodule"
```

## Agent Instructions

Before making changes, inspect `git status --short`, `README.md`, and `.gitmodules` if it exists. Keep commits small and intentional. If GitHub publishing is needed and `gh` is unavailable, prepare the exact commands for manual remote creation and push.
