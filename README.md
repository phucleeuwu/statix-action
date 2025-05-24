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

on: [push, pull_request]

jobs:
  statix:
    name: Statix Linting
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: cachix/install-nix-action@v25
      - uses: cachix/cachix-action@v14
        with:
          name: statix
      - uses: phucleeuwu/statix-action@v2
```

## ⚙️ Inputs

| Input Name       | Description                                 | Default Value |
|-----------------|--------------------------------------------|--------------|
| `flags`         | Command-line flags to Statix              | `fix`        |
| `author`        | Author of the commit                      | `${{ github.actor }} <${{ github.actor }}@users.noreply.github.com>` |
| `open_pr`       | Open pull request                          | `false`      |
| `exclude`       | Exclude directory                          | none         |
