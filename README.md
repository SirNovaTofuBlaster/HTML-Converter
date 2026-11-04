# HTML Converter

Upload an HTML file and get the same page back converted. Tags, images and layout stay exactly as they are.

Text is looked up in a database that lives in a separate **private** GitHub repo. This public repo contains only the website.

If some text isn't in the database yet, it is left as written, and the site offers a button that copies the list of missing texts so they can be added.

## Setup (once per computer)

1. Open the site and click ⚙.
2. **GitHub token:** create a fine-grained token with access to your private repo only, with **Contents → Read-only**.
3. **Private repo:** `your-username/your-private-repo`.
4. Click **Save**. Both are kept in that browser only.

## What goes in the private repo

For each language flag:

- `glossary-<code>.json`: the database of converted texts
- `rules-<code>.json` (optional): settings for that language, such as `htmlLang` (written into the converted page) and `swapDecimal` (`true` to switch between `.` and `,` in numbers when reusing a text)
