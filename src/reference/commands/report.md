# Reporting & Feedback (`report`)

`report` lets you send feedback to the ScriptSense author from inside Studio.

It supports:
- A dedicated **Report UI** (recommended)
- A quick **CLI draft** flow (legacy)

> Screenshot placeholder: Report UI main window  
> `![Report UI](report-feedback.png)`

#### ⚠️ Only use report to send plugin feedback; don’t include secrets (API keys, passwords, private links)!

---

## Usage

### UI mode (recommended)
- `report`

Opens the Report window.

### CLI mode (quick draft)
- `report <message>`
- `report bug <message>`
- `report suggestion <message>`
- `report security <message>`

CLI mode creates a pending draft and asks for confirmation.

### Aliases
- `feedback`
- `bug`
- `suggestion`
- `-n`

---

## Categories

You can choose one of:
- Bug
- Feedback
- Security
- Suggestion

In the UI, use the Category dropdown.  
In CLI mode, prefix the message with the category keyword (e.g. `bug ...`).

---

## Attach images (optional)

In the UI, click **Attach** and select:
- `.png`, `.jpg`, `.jpeg`

Images are uploaded to ImgBB and the resulting URLs are included with your report.

> Screenshot placeholder: attached image preview + “Attached Images” gallery  
> `![Attached images](report-gallery.png)`

### ImgBB setup
To enable uploads, set your API key:
- `config ImgBBKey <your_key>`

If no key is set, ScriptSense will show:
- “Error: Please set your ImgBB API Key in Settings.”

### Limits
- Upload body must be under ~1MB (ScriptSense rejects larger payloads).

---

## Include context (optional)

The report UI includes a toggle for sending a small context snapshot. When enabled, ScriptSense includes:
- ScriptSense version
- macro count
- whether Studio is in Edit or Run mode

> Note: Context is optional and can be disabled via the toggle.

---

## Cooldown

To prevent spam, reports are rate-limited:
- 60 seconds between sends

If you send too soon:
- “Please wait before sending another report.”

---

## CLI draft flow (legacy)

When you run `report <message>`, ScriptSense:
1) Parses the category (if provided)
2) Saves a pending draft
3) Logs a preview + asks whether to include context

If the report fails to send, ScriptSense keeps your text and asks you to retry.

> Screenshot placeholder: terminal output showing “Drafting report…” and confirmation prompt.

---

## Troubleshooting

### “Message cannot be empty.”
Your CLI message was empty. Use `report <message>` or open the UI with `report`.

### “Image too large!”
Try a smaller image (the upload body is limited to ~1MB).

### “Report failed. Your text has been saved.”
Sending failed, but your draft text was preserved. Try again (button changes to “Retry Sending”).
