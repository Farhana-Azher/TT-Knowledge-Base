# TTMATION Knowledge System

A searchable best practices repository for Transform Together's TTMATION AI upskilling programme.

**Live site:** _(add your GitHub Pages URL here once published)_

## What this is

This tool collects best practices, tips, and lessons learned from TTMATION training sessions
so the whole team can search, filter, and bookmark what's most relevant to them. Currently
covers 4 sessions and 75 best practices across 8 categories.

## Repo structure

```
ttmation-knowledge-system/
├── index.html                  ← the tool itself (served by GitHub Pages)
├── data/
│   └── best-practices.json     ← all best practices, as structured data
├── transcripts/                ← source meeting transcripts, for reference/audit
├── docs/
│   └── how-to-add-a-session.md ← instructions for adding new content
└── README.md                   ← this file
```

## How updates work

The tool (`index.html`) loads its content from `data/best-practices.json` at runtime.
To add new best practices, you only need to edit that JSON file — no need to touch the
HTML or JavaScript. See `docs/how-to-add-a-session.md` for the step-by-step process.

Once published to GitHub Pages, any change pushed to this repo goes live automatically
within a minute or two, at the same URL.

## Status

The "Add Best Practice" feature in the tool itself is currently **disabled** (admin decision,
June 2026). New content is added directly via `data/best-practices.json` for now.

## Maintained by

Fara — Business Analyst & Principal Consultant, Transform Together
