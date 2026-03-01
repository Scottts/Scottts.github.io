# Theme & UI Customization (`theme`)

ScriptSense supports **theme presets** and **per-key overrides** to customize the UI.

Theme changes are stored in `ThemeOverrides` (a JSON string in ScriptSense settings), and the `theme` command updates it automatically.

> Screenshot placeholder: Add a before/after of a preset (same screen, different theme)  
> `![Theme before/after](theme-before-after.png)`

---

## Quick start

### List current overrides + available presets
- `theme`
- `theme list`

### List presets only
- `theme presets`

### Apply a preset (overwrites all current overrides)
- `theme Midnight`
- `theme apply Midnight`
- `theme set Midnight`
- `theme use Midnight`

### Override a single theme key
- `theme set Button #ff0000`
- `theme set Text 240,240,240`

### Remove overrides
- `theme clear Button` *(removes one key override)*
- `theme reset` *(clears all overrides)*

> GIF placeholder: `theme presets` → apply preset → `theme set Text ...` → widget updates  
> `![Theme command demo](theme-demo.gif)`

---

## Command reference

### Usage
- `theme`
- `theme list`
- `theme presets`
- `theme <PresetName>`
- `theme apply <PresetName>`
- `theme use <PresetName>`
- `theme set <PresetName>`
- `theme set <Key> <Color>`
- `theme clear <Key>`
- `theme reset`

### Aliases
- `themes`
- `uitheme`

---

## Presets

In this snapshot (v2.17.0), the built-in presets include:

- Midnight
- Dracula-ish
- Nord
- Catppuccin Mocha
- Gruvbox Dark
- Tokyo Night
- Rose Pine
- Light Minimal
- Synthwave
- Forest
- Orange Joe

> **Note:** Preset lists can change between versions/builds.

> Screenshot placeholder: terminal output of `theme presets`  
> `![Theme presets output](theme-presets.png)`

---

## Theme keys

When you run `theme` / `theme list`, ScriptSense prints the **valid theme keys** (these come from `UIFactory.Theme` and only keys backed by an `EnumItem` are accepted).

If you try to set or clear an invalid key, ScriptSense will print a list of valid keys.

> Screenshot placeholder: an “Invalid theme key” error showing the valid keys list  
> `![Invalid theme key](theme-invalid-key.png)`

---

## Colors: supported formats

`theme` accepts exactly these formats:

- Hex: `#RRGGBB`
- RGB: `R,G,B` (0–255)

Examples:
- `theme set Accent #3b82f6`
- `theme set Text 235,235,235`

If the color is invalid, it prints:
- “Invalid color. Use #RRGGBB or R,G,B”

---

## What gets saved (ThemeOverrides)

Theme overrides are saved as JSON in `ThemeOverrides`.

### Shape:
- A JSON object mapping theme keys → **hex strings** (e.g. `"#FF0000"`)

### Example:
```json
{
  "Text": "#E6EDF3",
  "Button": "#21262D"
}
```

### Important details:

Values are stored as hex strings (even if you typed R,G,B).

Applying a preset overwrites the entire overrides table with the preset’s keys.


---

## Troubleshooting

### “Unknown theme preset”

Run theme presets and copy the preset name (matching is flexible, but spelling helps).

If you’re on a different version/build, the preset may not exist there.

### “Invalid theme key”

Run theme to see the valid keys list, then copy one of the keys exactly.

### “Invalid color”

Use #RRGGBB or R,G,B only (0–255).
