# HTML Converter

Upload an HTML file and get the same page back converted. Tags, images and layout stay exactly as they are.

Text that has been converted before is reused from your database, and only new text is sent to Claude.

This public repo contains only the website. Your database and your rules live in a separate **private** GitHub repo.

## Setup (once per computer)

1. Open the site and click ⚙.
2. **Claude API key:** create one at console.anthropic.com.
3. **GitHub token:** create a fine-grained token with access to your private repo only, with **Contents → Read and write**.
4. **Private repo:** `your-username/your-private-repo`.
5. Click **Save**. Everything is kept in that browser only.

## What goes in the private repo

For each language flag, one rules file that you write, and one database file that the site creates:

- `rules-<code>.json`, with these fields:
  - `instructions` (required): what Claude should do for this language
  - `htmlLang`: language code written into the converted page
  - `forbiddenWords` and `forbiddenPatterns`: answers containing these are rejected and retried once
  - `swapDecimal`: `true` if numbers should switch between `.` and `,` when reusing text
- `glossary-<code>.json`: created and updated automatically
