# HTML Converter

Upload an HTML file and get the same page back translated, with tags, images and layout kept as they are.

- **Languages:** European Portuguese (pt-PT). Finnish is planned.
- **Translations** come from your own Claude API key, and only for text that isn't in your database yet.
- **The database** (one `glossary-<language>.json` per language) lives in a separate **private** GitHub repo. This public repo contains only the website: no keys, no translations.

## Setup (once per computer)

1. Open the site and click ⚙ Settings.
2. **Claude API key:** create one at console.anthropic.com.
3. **GitHub token:** create a fine-grained token (GitHub → Settings → Developer settings → Fine-grained tokens) with:
   - Repository access: **only** your private database repo
   - Permissions: **Contents → Read and write**
4. **Database repo:** `your-username/your-private-repo`
5. Click **Save on this computer**.

Keys are stored only in that browser's local storage.

## Rules

- Portuguese output must be European Portuguese. Answers containing Brazilian-only wording are rejected and retried once; if still wrong, the text is left in English rather than saved.
- HTML tags inside sentences are sent as `[[0]]…[[/0]]` markers and must come back intact.
