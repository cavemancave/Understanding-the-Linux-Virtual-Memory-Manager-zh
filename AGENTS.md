# AGENTS.md — Working rules for AI agents in this repo

This file records the project owner's standing instructions. Agents (Copilot CLI, etc.) MUST follow these rules when working in this repository.

## Project status
Translation and figure work for the book is **complete**:
- All 28 source chapters (`understand001.html` … `understand028.html`) translated to Simplified Chinese.
- All figures converted to inline `<svg>` with Chinese labels.
- `understand029.html` is empty in the source and skipped.

These rules still apply to any future fix-ups, retranslations, or new content.

## Identity / commits
- Use the project's original git identity: `cavemancave <echooffapple@gmail.com>`.
- Set it per-worktree if the worktree's config differs:
  `git config user.name cavemancave && git config user.email echooffapple@gmail.com`.
- One file per commit. After each successful change to a file, create a commit immediately.
- Commit messages are written in **English** (the codebase content is bilingual, but commit history stays English).
- Push after every commit (`git push`), so progress is visible upstream.
- Include a `Co-authored-by: Copilot <198982749+Copilot@users.noreply.github.com>` trailer when an AI agent assisted.

## Translation work
- Source: `original_html/understandNNN.html` (English).
- Target: `translated_html/understandNNN_zh.html` (Simplified Chinese).
- Preserve original HTML structure, anchors, links, code blocks, tables.
- Translate `alt` text on images.
- Keep the link to `understand_zh.css` intact.

### Prose vs. code (especially in appendices)
- **Code blocks (`<PRE>` / `<pre class="verbatim">`) are not translated.** Keep identifiers, keywords, string literals, and `/* … */` or `//` comments inside the code byte-for-byte identical to the source.
- Only **prose between code blocks** is translated — paragraphs, headings, and the bulleted line-by-line explanations that follow each listing.
- C identifiers in prose stay in English (wrap in `<tt>` or `<code>`); only the surrounding natural-language sentence is translated.
- Verify by running `grep -c '<PRE' …` on both source and target — counts must match.

### Navigation and cross-reference links
- Links to sibling chapters (Prev / Next / Up / TOC and inline `<a href="understandNNN.html#anchor">…</a>` references) MUST point to the `_zh.html` version (every chapter is now translated).
- If a future new source chapter is added but not yet translated, leave its link as `../original_html/understandNNN.html#anchor` as a placeholder, then sweep when it is translated.

## Figures
- Figures in the Chinese HTML files are **inline `<svg>`** (not `<img>` to PNG); SVG text/labels are in Chinese.
- Convert one figure per commit: `Inline SVG for figure N in understandNNN_zh (Chinese labels)`.

## Commit message conventions (English)
- Translation: `Translate understandNNN to Chinese (chapter X / appendix Y)`
- Figure: `Inline SVG for figure N in understandNNN_zh (Chinese labels)`

## Sub-agent / fresh-context workflow (when a unit is large)
For non-trivial new translation or figure work, prefer a fresh sub-agent (separate context window) per file or per figure to avoid context attention deterioration. The sub-agent is responsible for committing and pushing before exiting; the main session only orchestrates and verifies.

For minor edits and fix-ups that fit in the main session, edit directly — no sub-agent needed.

## Progress tracking
- Long-lived rules: this `AGENTS.md`. Update when the owner's preferences change.
- Per-session plans (when needed): `plan.md` at the repo root.

