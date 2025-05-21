### RULESET.md — Unified Guidelines (2025-05-21)

> **Purpose**  Provide a single, authoritative style guide for code, documents,
> and supporting assets. Rules are ordered from most‐general to most‐specific.

---

## 1  Global Principles   🌐

| ID  | Rule                                                                                                                      |
| --- | ------------------------------------------------------------------------------------------------------------------------- |
| G-1 | **Readability first** — favour clear structure, ≤ 80 chars/line, and terse, helpful comments.                             |
| G-2  | **Precise Comments**; Each code block must include precise comments—critical, comprehensive, and succinct. When a technical implication or subtle detail requires special attention, a critical explanation should be included near the relevant lines of code to aid the reader’s understanding.                 |
| G-3 | **Tabs, not spaces** for all indentation (code, docstrings, Markdown, LaTeX).                                             |
| G-4 | **Keep history traceable** — never alter program logic while reformatting; use comments and git commits to record intent. |
| G-5 | **Output in the Chatting Session** — Do not prefer Canvas or a file output unless explicitly specified: directly answer in the chatting dialogue.       |
| G-6 | **Latest upload wins** — if a file with the same name re-appears, treat the newest content as authoritative.              |
| G-7 | **DO NOT DELETE** — if `DO NOT DELETE` or a similar phrase is encountered within a code or script, do not mistakenly delete the relevant code snippet.              |

---

## 2  Generic Scripting & Programming   🛠️

1. **Human-friendly layout**: short logical blocks, blank lines around comments, explicit sectioning.
2. **Cross-language fallback**: when no language-specific rule exists, adapt the existing rules such as Python sensibly.
3. **No long one-liners**: break complex statements for clarity; align assignment operators and parameters.
4. **Comment scope**: document any non-obvious branch, loop, or algorithmic trick; avoid repeating self-evident code.

---

## 3  Python — Module Docstrings & Inline Comments   🐍

| Section          | Key Requirements                                                                                                  |
| ---------------- | ----------------------------------------------------------------------------------------------------------------- |
| Header format    | Raw triple-quoted string: `r""" … """`, wrapped top & bottom by **exactly 80 dots**.                              |
| Mandatory blocks | `How to Use`, `Dependency`, `Functionality`, `IO Structure` (in this order, caps, blank line after each heading). |
| Alignment        | Use tabs; keep internal formatting neat and grid-like.                                                            |
| Emphasis         | No Markdown syntax; use plain “NOTE:” / “IMPORTANT:”.                                                             |
| Inline comments  | Concise English, ≤ 80 chars, tab-indented, placed **above** multi-line logic with a blank line before/after.      |
| Safe edits       | You may add or re-flow comments and docstrings, **never** change code behaviour.                                  |

---

## 4  Markdown Documentation   📄

1. Use `#`, `##`, `###` for hierarchy; avoid numeric prefixes in headings.
2. Optional emoji prefixes are allowed (`📐`, `🗂️`, `🔍`) if they aid scanning.
3. Ensure heading sequence matches logical flow for TOC generators.

---

## 5  LaTeX Tables   📊

| Rule | Description                                                                       |
| ---- | --------------------------------------------------------------------------------- |
| L-1  | **No vertical lines**; rely on whitespace and `booktabs` rules.                   |
| L-2  | **Full width**: always span `\textwidth`.                                         |
| L-3  | Use `tabularx`, `array`, or `booktabs` for automatic padding.                     |
| L-4  | **Caption on top**, concise, with `\vspace{0.5em}` before table body.             |
| L-5  | Horizontal rules: `\toprule`, `\midrule`, `\bottomrule` only.                     |
| L-6  | Column template: wrap with `@{}` to remove outer padding (e.g., `{@{} l X @{}}`). |

---

## 6  File-Specific Precedence   📁

*Always honour the newest file with a given name; identical filenames do **not** imply identical contents.* (See G-5.)

---

### End of RULESET.md (2025-05-21)