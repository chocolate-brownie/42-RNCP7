# Starting a New Project as a Git Submodule

Use this flow from the parent repository root:

```sh
cd /home/mgodawat/Documents/42-RNCP7
```

## 1. Create the Project Repository

Create the standalone project repository on GitHub first.

Example:

```text
git@github.com:chocolate-brownie/my-new-project.git
```

## 2. Add It as a Submodule

Add the new repository as a submodule in the parent RNCP7 repository:

```sh
git submodule add git@github.com:chocolate-brownie/my-new-project.git my-new-project
```

This keeps the project source code in its own repository while the RNCP7 parent repository stores only a pointer to it.

## 3. Update the Project Index

Add the project to `README.md`:

```md
- [My New Project](my-new-project/) - Short description of what it does.
```

## 4. Commit Parent Repository Metadata

In the parent repository, commit only the submodule metadata and documentation:

```sh
git add .gitmodules README.md my-new-project
git commit -m "add my new project submodule"
git push origin main
```

The parent repository should contain metadata such as `.gitmodules`, documentation, and the submodule pointer. Do not copy full project source code directly into the parent repository.

## 5. Work Inside the Project Repository

Project changes are committed from inside the project folder:

```sh
cd my-new-project
# edit files
git add .
git commit -m "describe project change"
git push origin main
```

## 6. Update the Parent Pointer After Project Changes

After pushing new commits inside the project repository, update the parent repository's submodule pointer:

```sh
cd /home/mgodawat/Documents/42-RNCP7
git add my-new-project
git commit -m "update my new project submodule"
git push origin main
```

## Cloning With Submodules

Clone the parent repository with all submodules:

```sh
git clone --recurse-submodules git@github.com:chocolate-brownie/42-RNCP7.git
```

If the repository was already cloned without submodules, initialize them afterward:

```sh
git submodule update --init --recursive
```
