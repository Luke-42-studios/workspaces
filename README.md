# Workspaces

Master workspace for organizing projects, libraries, and tools with cross-project dependencies.

## Structure

```
workspaces/
├── libs/          # Shared libraries & frameworks (dependencies for other projects)
├── engines/       # Game/rendering engines
├── agents/        # AI/automation agents & assistants
├── projects/      # Active development projects
├── tools/         # Development tools & utilities
├── sandbox/       # Experiments, learning, prototypes
└── config/        # Shared system configurations
```

## Directory Conventions

| Directory   | Purpose                                           | Git Policy                    |
|-------------|---------------------------------------------------|-------------------------------|
| `libs/`     | Reusable libraries other projects depend on       | Independent repos             |
| `engines/`  | Game engines, rendering frameworks                | Independent repos (or clones) |
| `agents/`   | AI agents, automation tools, assistants           | Independent repos             |
| `projects/` | Active products/apps being developed              | Independent repos             |
| `tools/`    | Dev productivity tools                            | Independent repos             |
| `sandbox/`  | Throwaway experiments, learning projects          | Optional git                  |
| `config/`   | Dotfiles, system configs                          | Independent repo              |

## Creating New Projects

### Agent Quick Guide

When creating a new project, ask these questions:

1. **What is it?**
   - A reusable library others will depend on → `libs/`
   - A game engine or rendering framework → `engines/`
   - An AI agent or automation assistant → `agents/`
   - An app, game, or product → `projects/`
   - A dev tool or utility → `tools/`
   - Just experimenting/learning → `sandbox/`

2. **What should it be called?**
   - Use lowercase with hyphens: `my-project-name`

3. **Create it:**
   ```bash
   cd ~/workspaces/<directory>
   mkdir <project-name>
   cd <project-name>
   git init
   ```

4. **Does it depend on other workspace items?**
   - If yes, update the Dependency Map below

### Manual Steps

1. **Choose the right directory** based on purpose (see table above)
2. **Initialize as independent git repo** - each project manages its own history
3. **Document dependencies** in project README and update dependency map below
4. **Use relative paths** when referencing sibling projects: `../../libs/clay`

## Naming Conventions

- Use lowercase with hyphens: `my-project-name`
- Be descriptive but concise
- Prefix experiments in sandbox with date if throwaway: `2025-01-test-thing`

## Dependency Map

Projects and their dependencies on other workspace items:

| Project                  | Depends On                  | Notes                        |
|--------------------------|-----------------------------|-----------------------------|
| `projects/persona`       | `libs/clay`, `engines/SDL`  | UI framework + rendering    |
| `projects/games/*`       | `engines/godot` or `SDL`    | Game projects               |
| `projects/ollama-models` | -                           | Standalone Python           |

## Current Inventory

### libs/
- **clay** - High-performance UI layout library (C, header-only)

### engines/
- **godot** - Godot game engine
- **SDL** - Simple DirectMedia Layer

### agents/
- *(empty - future agent projects)*

### projects/
- **games/** - Game projects
  - `source-control` - Active game project
- **persona** - C++ application using Clay + SDL
- **ollama-models** - Python tooling for Ollama

### tools/
- **get-shit-done** - Project management CLI tool

### sandbox/
- **c-sample** - C learning/experiments

### config/
- System configuration files

## Setup

To clone a specific project:
```bash
cd ~/workspaces/projects
git clone <repo-url> project-name
```

To set up dependencies for a project, check its README for required libs/engines.
