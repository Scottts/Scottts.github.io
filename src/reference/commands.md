# CLI Commands

ScriptSense comes with a powerful Command Line Interface (CLI) to manage your projects.

## Core Commands

### `ssense init`
Initializes a new ScriptSense project in the current directory.
- **Usage**: `ssense init [options]`
- **Options**:
  - `--force`: Overwrite existing config files.

### `ssense check`
Runs the static analyzer on your project.
- **Usage**: `ssense check [path]`
- **Example**: `ssense check src/`

### `ssense watch`
Watches for file changes and re-runs analysis automatically.
- **Usage**: `ssense watch`

## Configuration

### `ssense config`
Manage your configuration settings.
- **Usage**: `ssense config [key] [value]`
- **Example**: `ssense config theme dark`