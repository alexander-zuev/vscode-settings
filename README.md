# VS Code Settings Repository

This repository contains my personal development environment configurations, primarily focused on editor settings for different development contexts (VS Code, Windsurf, and Cursor).

## What's Inside

- **VS Code / Windsurf / Cursor Settings**: Configuration files for different editors and development contexts
  - `vscode/global-settings.json`: Common settings shared across all environments
  - `vscode/frontend/frontend-settings.json`: Settings optimized for frontend development
  - `vscode/backend/backend-settings.json`: Settings optimized for Python/backend development
  - `vscode/windsurf-settings.json`: Windsurf-specific settings

## How It Works

This repo uses symbolic links to connect the configuration files in this repository to the actual configuration locations used by the applications. This means:

1. You edit the files in this repository
2. The changes are automatically reflected in your editors
3. Your configurations are version-controlled and can be easily transferred between machines

## Current Symlinks

- Windsurf settings:
  ```
  ~/Library/Application Support/Windsurf/User/settings.json → ~/vscode-settings/vscode/windsurf-settings.json
  ```

## How to Set Up on a New Machine

1. Clone this repository:
   ```bash
   git clone https://github.com/alexander-zuev/vscode-settings.git ~/vscode-settings
   ```

2. Create symlinks for the configurations you want to use:
   ```bash
   # For Windsurf
   ln -s ~/vscode-settings/vscode/windsurf-settings.json ~/Library/Application\ Support/Windsurf/User/settings.json

   # For Cursor (frontend projects)
   ln -s ~/vscode-settings/vscode/frontend/frontend-settings.json ~/Library/Application\ Support/Cursor/User/settings.json

   # For Cursor (backend projects)
   # ln -s ~/vscode-settings/vscode/backend/backend-settings.json ~/Library/Application\ Support/Cursor/User/settings.json
   ```

## Key Features

### Frontend Development Settings
- TypeScript import optimization
- Tailwind CSS file associations
- ESLint and Prettier integration
- Format on save enabled

### Backend Development Settings
- Python linting with Ruff
- Type checking with mypy
- Optimized file exclusions for Python projects
- JetBrains-like theme and configuration

## Why "dotfiles"?

The term "dotfiles" comes from Unix/Linux tradition where configuration files often start with a dot (`.`), making them hidden files. While not all files in this repo start with dots, the name has become standard for personal configuration repositories.

## Maintenance Notes

When making changes to your editor settings:
1. Edit the files in this repository, not the symlinked files
2. Commit and push changes to keep your configurations backed up
3. When setting up a new machine, clone this repo and create the necessary symlinks

## Future Improvements

- Add shell configurations (`.zshrc`, etc.)
- Add Git configurations (`.gitconfig`)
- Create a setup script to automate symlink creation
