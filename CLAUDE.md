# Workspaces Context

This is the master workspace for organizing projects with cross-dependencies.

## Structure

| Directory   | Purpose                                    |
|-------------|--------------------------------------------|
| `libs/`     | Reusable libraries (dependencies)          |
| `engines/`  | Game/rendering engines                     |
| `agents/`   | AI agents & automation assistants          |
| `projects/` | Active apps, games, products               |
| `tools/`    | Dev tools & utilities                      |
| `sandbox/`  | Experiments, learning, prototypes          |
| `config/`   | Linux dotfiles & system configuration      |

## Creating New Projects

Ask these questions:
1. **What is it?** → determines folder (see table above)
2. **Name?** → lowercase-with-hyphens
3. **Dependencies?** → update README.md dependency map

Then: `mkdir <dir>/<name> && cd <dir>/<name> && git init`

## Current Projects

- `libs/clay` - UI layout library (C)
- `engines/godot`, `engines/SDL` - Game engines
- `projects/persona` - C++ app (uses clay + SDL)
- `projects/games/source-control` - Game project
- `projects/ollama-models` - Python Ollama tooling
- `tools/get-shit-done` - Project management CLI

## Key Files

- `README.md` - Full conventions, dependency map, inventory
- `config/` - Dotfiles repo (https://github.com/Luke-42-studios/dotfiles)
