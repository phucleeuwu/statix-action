# Statix Action 🚀

A GitHub Action to **lint and fix Nix code** using [Statix](https://github.com/nerdypepper/statix), then **commit and push** the changes automatically.

## 📌 Features
- Runs **Statix** to **analyze and fix** Nix code.
- Automatically **commits** and **pushes** fixes to the repository.
- Uses [Nix](https://nixos.org/) for efficient dependency management.

## 🚀 Usage

To use **Statix Action** in your workflow, add the following to `.github/workflows/statix.yml`:

```yaml
name: Statix Linter

on:
  workflow_dispatch:
  push:

jobs:
  statix:
    name: Statix Linting
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@main
      - uses: cachix/install-nix-action@v31
      - uses: phucleeuwu/statix-action@v2
```

## ⚙️ Inputs

Input | Description | Default
-- | -- | --
flags | Command-line flags to Statix | fix
author | Author name and email | ${{ github.actor }} <${{ github.actor }}@users.noreply.github.com>
committer | Committer name and email | GitHub <noreply@github.com>
directory | Directory to scan | .
commit_message | Git commit message | Chore: Fix Nix code with Statix
open_pr | Whether to create a pull request instead | false



