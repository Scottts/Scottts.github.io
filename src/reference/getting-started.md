# Getting Started

ScriptSense is designed to be “add it and forget it.”

Once installed, you can simply open a script and ScriptSense will surface useful project info automatically (code health, tasks, unused variables, broken paths, and more). The terminal / command palette is optional.

---

## Install

1) Open the ScriptSense asset page and add it to your inventory:

	https://create.roblox.com/store/asset/75708311511053/ScriptSense

2) In Roblox Studio, install it from either:
	- Your inventory (Plugins → Manage Plugins / My Plugins), or
	- Toolbox → **Plugins** tab → find ScriptSense → install

3) That’s it.

---

## First Use

1) Open any script (Script / LocalScript / ModuleScript).
2) ScriptSense will show a widget with live insights like:
	- Code health
	- Tasks (TODO/FIXME/HACK)
	- Unused variables
	- Broken paths / dependency issues
	- Other project signals depending on what’s available

**You don’t need to run a command for this.**

---

## Optional: Open the Command Palette / Terminal

If you *do* want to use commands:

- Open the **Plugins** section in the Studio toolbar and open ScriptSense’s palette/terminal from there.

Some useful first commands:
- `help` — list commands / get help for one command
- `scan` — scan for issues and dead code
- `tasks` — open the Tasks hub
- `docs` — open this documentation
- `theme` — change theme presets / tweak UI colors

---

## Troubleshooting

### I installed it, but nothing shows up
- Try opening a script first and add something like `getfenv()` (ScriptSense reacts to an active script).
- Make sure the plugin is enabled in Studio (Plugin Management).

### The terminal isn’t showing
- The terminal is optional. ScriptSense features still work without it.
- Open it from the Studio toolbar’s **Plugins** section.

---
