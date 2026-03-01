FAQs & Troubleshooting
> ScriptSense FAQs and quick fixes for common issues. Learn what ScriptSense is (and isn’t), how it fits with Rojo/LSP tools, and how to resolve the most frequent setup, performance, and rule-related questions.
---
## FAQ: Why ScriptSense (and how is it different from Rojo / LSP tools)?

### **Is ScriptSense a Rojo replacement?**
* No. Rojo is for syncing files between an external editor and Studio. ScriptSense is a **Studio-native workflow tool** for analysis, tasks, navigation, and refactors without leaving Studio.

### **What problem does ScriptSense solve?**
* It reduces “Studio friction” by surfacing **code health**, **tasks (TODO/FIXME/HACK)**, **unused variables**, and **broken paths**, and by giving you a **Command Palette** to run actions quickly.

### **Who benefits the most from ScriptSense?**
* It’s most valuable for **teams and medium-to-large projects**, where people refactor often, code ownership is shared, and consistency checks + navigation speed matter.

### **Why not just use Luau LSP / Selene in VS Code?**
* Those are great for external-editor diagnostics. ScriptSense focuses on **in-Studio workflows** — where you test, wire instances, review scripts, and apply quick project-aware actions.

### **Will ScriptSense slow down Studio?**
* It’s designed for real projects: it uses **indexing/caching** and supports **targeted workflows** (current script vs project-wide). If your project is huge, you can tune settings to reduce scanning overhead.

### **Does ScriptSense send my code anywhere (privacy)?**
* By default, **no** — analysis runs locally in Studio and does **not** use the internet.

### **Does ScriptSense use networking at all?**
* Only if you **explicitly run the `report` command**. Nothing is sent automatically.

### **What does the `report` command send?**
* Your report message and relevant debugging context (for example: plugin version, Studio version, and command output/logs). If code snippets are ever included, that should be **clearly shown and opt-in** before sending.

### **Is it safe to try refactors and tools?**
* ScriptSense includes **snapshots/backups** to help you recover from mistakes or crashes, making it safer to experiment — especially when applying refactors.

---

# Troubleshooting

### **ScriptSense isn’t showing up anywhere. What should I check first?**
* Make sure ScriptSense is enabled in **Plugins**, then look for the **Terminal** button in the plugin toolbar. If you don’t see it, restart Studio and confirm the plugin is installed (Manage Plugins).

### **The Terminal / Command Palette won’t open.**
* Try restarting Studio, then open it from the ScriptSense toolbar button. If Studio UI is “stuck,” close any floating plugin widgets and reopen the Terminal.

### **The widget panel (code health / tasks / suggestions) isn’t appearing.**
* The widget only opens when ScriptSense has something to flag (rule violations, unused variables, broken paths, or tasks). To confirm it’s working, add something obvious like `getfenv()`, `wait()`, or a `TODO:` comment in an open script.

### **Commands run, but nothing happens / no output appears.**
* Make sure a Script is open (some commands need an active editor context). If you’re running project-wide commands, verify the project can be indexed (large places may take longer on first run).

### **ScriptSense feels slow or causes lag.**
* Reduce workload by switching to **current-script scanning**, disabling always-on watchers (like watchdog-style scanning), and limiting heavy checks. Large projects benefit from letting the initial index finish, then using cached results.

### **The first scan is taking a long time.**
* First runs typically build a project index (scripts/modules/dependencies). After the index exists, scans should be faster due to caching.

### **I’m seeing warnings that don’t seem correct (false positives).**
* ScriptSense is best at static patterns; dynamic code (runtime instance creation, dynamic `require`, metatable-heavy patterns) can confuse analyzers. Use ignore/disable options or adding a simple `-- ss-ignore` comment on the line(s) for specific rules or narrow scans to the current script when needed.

### **Why does it flag `wait()` / `getfenv()`?**
* Some rules intentionally discourage deprecated/unsafe patterns. If your use case is intentional, add a `-- ss-ignore` comment on the line(s).
> **Note:** Linter rules will be exposed in a later update for editing.

### **It says “broken path,” but the game runs fine.**
* Broken path checks are static. If the instance is created at runtime or inserted later, it may warn even if it works at runtime. Consider adding rule exceptions for known dynamic patterns.

### **Rename/refactor didn’t update everything.**
* Refactors are safest on statically-resolvable references. If your project uses dynamic access (`obj[name]`, string-built paths, dynamic requires), some usages can’t be updated reliably.

### **Undo/redo didn’t restore what I expected after a refactor.**
* Use ScriptSense history/snapshots when available, and check whether changes were applied across multiple scripts. For large edits, restoring a snapshot is often the quickest recovery option.

### **Where are backups/snapshots stored and how do I restore them?**
* Snapshots are stored by ScriptSense for recovery. Use the History/Snapshots command(s) in the Terminal to browse and restore the version you want.

### **ScriptSense isn’t detecting my TODO/FIXME comments.**
* Make sure you’re using supported tags (for example `TODO:` / `FIXME:`) inside comments. Custom task tags aren’t supported yet.

### **Team projects: different people get different results.**
* Ensure everyone is using the same ScriptSense version and the same configuration. If your team supports shared config/macros, sync or export/import settings so the rules and filters match.

### **How do I reset ScriptSense to default settings?**
* Use the Config/Settings command(s) to restore defaults, or clear ScriptSense’s saved settings via Studio’s plugin settings management (then restart Studio).

### **How do I report a bug or send feedback?**
* Use the `report` command and include: what you expected, what happened, how to reproduce it, and your Studio/plugin version. Only the `report` command uses networking; normal scanning runs locally.

---

### Helpful links
- **[Getting Started](getting-started.md)** 
- **[Commands & Terminal](commands.md)** 
- **[Changelogs](changelogs.md)**
