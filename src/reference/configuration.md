# Configuration

ScriptSense settings are stored as plugin settings (per-user) and can be edited through the `config` command.

Project-level macros (shared with your place/team) are stored in `ServerStorage/ScriptSense_Data/ProjectMacros`.

---

## Editing settings

Use the `config` command:

- `config` → list settings
- `config (Key)` → show a specific setting
- `config (Key) (Value)` → set a value

Examples:
- `config DynamicScanningEnabled false`
- `config DebounceTime 0.25`
- `config NotifyPosition TopRight`

---

## Settings (Schema)

| Key | Type | Default | What it does |
|---|---|---:|---|
| SmartImports | Toggle | false | Smart Imports |
| AutoSaveEnabled | Toggle | true | Auto-Save History |
| AutoRefactor | Toggle | false | Automatically applies refactors on manual changes |
| BranchedHistory | Toggle | false | Git-like Branch History |
| UseDedicatedSpecFolder | Toggle | true | Store `.spec` files in `ScriptSense_Data` |
| ImgBBKey | String | `""` | ImgBB API Key (required for uploads) |
| ThemeOverrides | String | `"{}"` | UI theme override JSON |
| DynamicScanningEnabled | Toggle | true | Real-time Scan |
| ShowWidget | Toggle | true | Show Widget on Start |
| WidgetPersists | Toggle | false | Widget no longer auto-closes |
| CaseInsensitive | Toggle | true | Case Insensitive Search |
| AutoSyncProject | Toggle | true | Sync Project Macros |
| SmartRecovery | Toggle | true | Crash Recovery |
| WatchdogInterval | Num | 60 | Watchdog Interval |
| DebounceTime | Num | 0.5 | Debounce Time (seconds) |
| NotifyEnabled | Toggle | true | Enable Notifications |
| HideNotify | Toggle | false | Hides the notification UI |
| NotifySound | Toggle | false | Enables/disables notification sound |
| NotifyVolume | Num | 0.1 | Adjusts notification sound volume |
| NotifyPosition | Dropdown | BottomLeft | Notification Position (`BottomRight`, `BottomLeft`, `TopRight`, `TopLeft`) |
| NotifyDuration | Num | 6 | Toast Duration (seconds) |
| ScanOnMove | Toggle | true | Scan on Move (Refactor) |

---

## ThemeOverrides (JSON)

`ThemeOverrides` is a JSON string stored in settings.  
It should be a JSON object (`{}`) containing per-key theme overrides used by the UI/theme system.

(If you use the `theme` command, it should update this setting automatically.)

---

## ProjectMacros (shared macros)

ScriptSense supports two macro layers:

- **Global macros**: stored in plugin settings (per-user).
- **Project macros**: stored in `ServerStorage/ScriptSense_Data/ProjectMacros` (shared with the place).

The project macro module is watched for changes; when it updates, ScriptSense refreshes the project macro layer automatically.
