# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

A single deliverable: the `perlbrew` file, a Bash completion script for [perlbrew](https://perlbrew.pl/).
Everything else (`README.md`, `CONTRIBUTING.md`, dotfiles, `.github/`) is documentation and lint
configuration. There is no build step, no test suite, and no release/versioning process.

## The completion script

`perlbrew` defines `_perlbrew()` and registers it with `complete -F _perlbrew perlbrew`. The function
dispatches on the previous word (`prev`):

- `use` / `uninstall` → completions from `perlbrew list`
- `install` → completions from `perlbrew available`, filtered to exclude `.tar.bz2` lines

Adding support for another subcommand means adding another `elif [[ "${prev}" == "..." ]]` branch that
populates `COMPREPLY` via `compgen -W`. Tested only against Bash 3.

## Validation

All checks run in GitHub Actions `on: push` (`.github/workflows/`). To reproduce locally:

- **shellcheck**: `shellcheck perlbrew` — `.shellcheckrc` disables `SC2148`, `SC2207`, `SC2086`
  (missing shebang, unquoted `compgen` word-splitting, and unquoted `$cur` are intentional for a
  completion snippet; keep them disabled rather than "fixing" the style).
- **markdownlint**: config `.markdownlint.json` (default rules, line-length off).
- **editorconfig-checker**: `.editorconfig` / `.ecrc`. General style is 4-space indent, LF, final
  newline, no trailing whitespace; YAML is 2-space; the `perlbrew` file itself has `tab_width = 8`
  and no max line length.
- **spellcheck** (pyspelling + aspell): adding a legitimate new word means appending it to
  `.wordlist.txt`. `dictionary.dic` is a generated aspell artifact — do not hand-edit it.
