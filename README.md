# 42 RNCP7 Portfolio

This repository will organize my RNCP7-level projects as an ongoing portfolio. Each project will live in its own GitHub repository and be linked here as a submodule, keeping the main repository clean while preserving independent project histories.

## Planned Structure

```text
42-RNCP7/
  README.md
  .gitmodules
  projects/
    project-name/
```

## Working With Submodules

Clone this repository with all linked projects:

```sh
git clone --recurse-submodules git@github.com:chocolate-brownie/42-RNCP7.git
```

Initialize submodules after cloning:

```sh
git submodule update --init --recursive
```

## Project Index

- [RNCP7 Dashboard](projects/rncp7-dashboard/) - React dashboard for tracking RNCP7 portfolio projects, progress, and roadmap views.
