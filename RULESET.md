## ✅ Rule for Handling Uploaded Files with Matching Filenames

When the user uploads a file via prompt (e.g., `fs_to_html.py`),
**you must treat the newly uploaded file as authoritative**,
even if a previously known file with the same name exists in memory.

> ⚠️ In other words: identical filenames do **not** imply identical content.
> Always resolve ambiguity in favor of the most recently uploaded file.

This is critical to avoid misinterpretation when file contents have changed
but the filename remains the same.

---

## ✅ Generic Principle for Scripting and Programming

* `Care Human Readability` — avoid lengthy lines (beyond 80 characters per line), complicated structure, and lack of friendly comments.

---

## ✅ Rules for Python Module Header Docstring and Inline Comments

These rules define the required format for both:

* the **module-level docstring** at the top of each standalone Python script
* the **inline comments** throughout the code

### 1. **Raw String Format for Header**

Use a raw triple-quoted string:

```python
r""" ... """
```
followed by a blank line before starting the script, which preserves formatting such as tabs and backslashes. An example structure of the docstring reads:
```python
r"""................................................................................

How to Use:

	python fs_to_html.py

................................................................................

Dependency:

	pip install gitignore-parser==0.1.12

................................................................................"""
```

### 2. **Visual Divider**

Surround the docstring content with **exactly 80 dots (`.`)** on top and bottom, and between sections, to provide clear visual boundaries.

### 3. **Mandatory Sections**

Each module docstring must include the following sections in this order:

* `How to Use` — shows a basic CLI usage example.
* `Dependency` — lists exact `pip install` command(s) with version.
  (Use tabs for shell command indentation.)
* `Functionality` — Provide a succicnt but comprehensive and intuitive summary on what is being done within the code or script.
* `IO Structure` — Provide a succinct explanation on the IO structure as necessary.

### 4. **Style and Alignment**

* Section titles must be **capitalized** and followed by a blank line.
* Maintain clear visual alignment inside each section.
* Use tabs instead of spaces for indentation (in both docstrings and code examples).

### 4.1 Avoid Markdown Syntax Inside Python Strings

* Avoid using `**bold**`, `_italic_`, or backtick-enclosed `inline code` inside Python docstrings unless absolutely necessary.
* If emphasis is required, use plain text alternatives such as:

  * `"NOTE:"`, `"IMPORTANT:"`, or all caps keywords.

### 5. **Inline Commenting Rules**

The following rules govern inline comments in all scripts:

* Add **inline comments for all non-trivial logic**, conditionals, and loops.
* Comments must be precise, short, and written in **plain English**.
* Avoid restating what the code already makes obvious.
* For multi-line logic, precede the code with a **block comment** (with blank lines before and after).
* Use tab indentation for comment alignment, and limit lines to **≤ 80 characters**.

### 6. **Scope of Modification**

When enriching a script with docstrings or comments:

* ✅ You **may add** docstrings, inline comments, and blank lines for clarity.
* ✅ You **may improve** line breaks and alignment to improve readability.
* ❌ You **must not change** the original code's logic or functionality in any way.

This ensures that annotations are safe and audit-proof.

### 7. **Purpose**

This combined rule helps ensure that all scripts:

* Are self-explanatory when read in isolation.
* Remain executable without alteration.
* Maintain long-term readability and onboarding clarity.

---

## ✅ Rules for Sectioning in Markdown

When documenting in `README.md` or related Markdown files:

* Use heading levels `#`, `##`, `###` to represent document structure.
* Do **not** use numeric prefixes like `1.`, `2.`, etc. in the heading text.
* To improve readability, optionally prefix headings with **visual emojis** (e.g., `📐`, `🗂️`, `🔍`).
* Heading structure must remain consistent with document logic and GitHub Markdown rendering.

This avoids confusion and ensures compatibility with auto-generated Table of Contents tools.

---

## ✅ Rules for LaTeX Tables

These rules define how all LaTeX tables should be formatted by default:

1. **No Vertical Lines**
    All tables must avoid vertical rules. Use spacing and alignment for clarity instead.

2. **Full Width**
    The table should always span the full `\textwidth`.

3. **Internal Padding via Packages**
    Automatic inner padding should be provided by using table environments like:
    - `tabularx`
    - `array`
    - `booktabs`

4. **No Manual Margins**
    Avoid inserting manual `\hspace`, `\quad`, or `~` for spacing inside cells.
    Proper layout must rely on the structure and package settings.

5. **Table Caption Rules**
    - The caption must appear **above** the table.
    - The caption must be **concise and intuitive**, summarizing the content clearly.
    - Add a small vertical space (e.g., `\vspace{0.5em}`) between the caption and the table body for better readability.

6. **Booktabs Rule System**
    Use `\toprule`, `\midrule`, and `\bottomrule` instead of `\hline` for elegant horizontal lines.

7. **Alignment Template**
    Use `@{}` on the outer sides of column specifications to remove default padding.
    Inside, use `l`, `c`, `X`, etc., as needed.
    For example:
    \`\`\`latex
   \begin{tabularx}{\textwidth}{@{} l X @{}}

---