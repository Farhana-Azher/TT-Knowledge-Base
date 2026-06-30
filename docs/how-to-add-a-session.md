# How to add a new TTMATION session

When a new TTMATION training session happens, follow these steps to get its best
practices into the Knowledge System.

## 1. Save the transcript

Drop the session transcript (`.docx` or `.txt`) into the `transcripts/` folder.
Name it something like `session-3-yourname.docx` to keep things consistent.

## 2. Extract best practices using Claude

Open `index.html` (the live site or a local copy) and use the **Extract from
Transcript** tab inside "Add Best Practice" to generate a structured extraction
prompt, OR paste your transcript directly into Claude.ai with a prompt like:

> You are a knowledge extractor for Transform Together's TTMATION programme.
> Read the transcript below and extract every best practice mentioned. For each
> one, return a JSON object with: title, desc, category (one of: prompting,
> context, testing, architecture, workflow, collaboration, models, mindset),
> contributor, tags (array), source. Return ONLY a JSON array, no other text.

## 3. Add the new entries to the data file

Open `data/best-practices.json` in GitHub's web editor (or locally).

For the exact format to copy-paste, use **`data/TEMPLATE-new-entry.json`** — it has
a blank template, the list of valid categories, and a filled-in example side by side.
That file is just a reference; it's never loaded by the tool itself.

Each entry follows this shape:

```json
{
  "id": 61,
  "category": "prompting",
  "session": 3,
  "contributor": "Jane Smith",
  "title": "Short, actionable title",
  "desc": "2-4 sentence explanation of the practice.",
  "tags": ["keyword1", "keyword2"],
  "source": "Session 3 Demo"
}
```

- **`id`**: must be unique — open `data/best-practices.json`, find the highest existing
  `id`, and use the next number up
- **`category`**: must be exactly one of the 8 valid values (see the template file)
- **`session`**: the session number this came from

Paste your new entries into the array (don't forget the comma between entries),
save, and commit the change with a message like `Add Session 3 best practices`.

**Quick sanity check before committing:** JSON is strict about commas and quotes.
If you're not sure your edit is valid, paste the whole file into
[jsonlint.com](https://jsonlint.com) — it'll tell you immediately if something's broken,
before it breaks the live site.

## 4. Check it live

GitHub Pages updates automatically within a minute or two of your commit. Refresh
the live site and confirm the new practices appear and the stats count is correct.

## Re-enabling "Add Best Practice" in the tool

The in-tool "Add Best Practice" button is currently disabled. To turn it back on,
find this line near the top of the `<script>` section in `index.html`:

```js
const ADD_BEST_PRACTICE_ENABLED = false;
```

Change it to `true`, save, and commit.
