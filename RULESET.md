### RULESET.md — Unified Guidelines (2025-05-23)

> **Purpose**  
> This file serves as a unified and authoritative guideline for code, documents,  
> and supporting assets across the project.  
> It defines both human and AI-facing conventions, ensuring clarity, consistency,  
> and maintainability from development to delivery.

> ⚠️ AI developers (e.g., ChatGPT, Copilot) are expected to read and follow  
> this RULESET explicitly. This document is your shared contract with the AI.

---

## 1  Global Principles   🌐

| ID   | Rule                                                                                                                      |
|------|---------------------------------------------------------------------------------------------------------------------------|
| G-1  | **Readability first** — favor clear structure, ≤ 80 characters per line, and concise yet helpful comments.               |
| G-2  | **Precise English Comments only** — All comments must be written in clear, precise English. No other language allowed.    |
|      | Comments must be critical, succinct, and technically informative. Explain subtle logic or assumptions inline where needed. |
| G-3  | **Use tabs, not spaces** — Applies to code, docstrings, Markdown, and LaTeX.                                              |
| G-4  | **Keep history traceable** — Never alter program logic during reformatting. Use comments and commits to explain intent.  |
| G-5  | **Output in chat only** — All assistant replies must appear in the chat window unless explicitly asked otherwise.         |
| G-6  | **Latest upload wins** — Always treat the most recently uploaded file as authoritative.                                   |
| G-7  | **DO NOT DELETE** — Do not remove any comment or code block marked with this phrase unless it's demonstrably obsolete.    |
| G-8  | **No Canvas (ChatGPT only)** — Scripts, outputs, and updates must be shown in this chat session, not in canvas panels.    |

---

## 2  Generic Scripting & Programming   🛠️

1. **Human-friendly layout**  
   → Use short logical blocks, insert blank lines around comments, and structure sections clearly.

2. **Cross-language fallback**  
   → In the absence of a language-specific rule, follow Python-style conventions (e.g., docstring structure).

3. **No long one-liners**  
   → Break up complex logic for clarity. Align operators and argument lists when beneficial.

4. **Comment scope**  
   → Every non-trivial loop, branch, or algorithm must have a clear comment above it.  
   Do not comment the obvious. Favor meaningful guidance.

5. **Multiline comments**  
   → Always use the multiline comment syntax supported by the language  
   (e.g., `/* ... */` in JS/TS, `"""..."""` in Python).  
   Avoid repeating `//` or `#` across lines.

6. **Precise + Inclusive Explanation**
   → Comments and docstrings should be crafted to aid understanding for  
   technically skilled contributors from **different backgrounds**.

   🧠 Example:  
   A mathematician working on reinforcement learning and order-book modeling  
   might not be fluent in generic web frameworks (e.g., FastAPI, Vite).  
   A well-placed docstring like:

       "FastAPI is a stateless web API server that helps you construct
        REST endpoints in Python quickly and safely."

   ...makes the project more accessible, especially in AI-augmented workflows  
   where explanations are dynamically reused by the assistant.

   📌 Sub-discipline-specific jargons often create communication inefficiency.  
   Favor clear definitions and structured analogies over insider shorthand.

   ✅ Aim for:
   - precise, one-line definitions for libraries or concepts
   - conceptual analogies if appropriate (e.g., "FastAPI ~ stateless mapping")
   - minimal but useful scaffolding for context

   ❌ Avoid:
   - assuming domain familiarity (e.g., frontend routing, Docker internals)
   - bloated general-purpose introductions

   ✨ Think of each comment as onboarding your future self — or your AI pair.


---

## 2A  Global Docstring for Main Entry Points   📘

This rule governs files like `main.ts`, `main.py`, or other top-level orchestration scripts.

These scripts often coordinate multiple components (e.g., frontend + backend),  
so they should begin with a structured multiline docstring that provides the high-level context  
for both human readers and AI assistants.

🟦 Target Format:

```ts
/** ============================================================================
 * Project Overview:
 * Frontend Technology:
 * Backend Integration:
 * How to Run (Dev Only):
 * Limitation:
 * TODO (DO NOT DELETE):
 * ============================================================================
 */
````

🟡 Guidelines:

* This format serves as a **long-form metadata block**, meant to evolve across the project's lifecycle.
* It is not required at project start but should be fully populated by the delivery or review stage.
* You may extend or omit sections as appropriate, but follow the structural intent.
* Example API endpoints (GET/curl), runtime versions, and key filenames are encouraged.

🧠 Note:
This docstring structure is designed with AI-assisted comprehension in mind.
Think of it as a persistent onboarding layer for both your teammates and your future self.

---

## 3  Python — Module Docstrings & Inline Comments   🐍

| Section          | Rule                                                                                                              |
| ---------------- | ----------------------------------------------------------------------------------------------------------------- |
| Header format    | Use raw triple-quoted string `r""" ... """`, enclosed with **exactly 80 dots** on top and bottom.                 |
| Mandatory blocks | Must contain (in order): `How to Use`, `Dependency`, `Functionality`, `IO Structure`. Each block title is capped. |
| Alignment        | Use tabs for all indentation. Maintain internal layout grid-style.                                                |
| Emphasis         | Use `NOTE:` or `IMPORTANT:` — do not use Markdown formatting.                                                     |
| Inline comments  | Write concise English (≤ 80 chars), tab-indented, placed above multi-line logic with a blank line before/after.   |
| Safe edits       | You may reformat or comment, but must not alter logic or behavior.                                                |

---

## 4  Markdown Documentation   📄

1. Use `#`, `##`, `###` for heading levels. Do not prefix headings with numbers.
2. Emoji prefixes (`📐`, `🔍`, `🧩`) are allowed if they improve skimming.
3. Ensure headings follow a logical order for TOC generation.

---

## 5  LaTeX Tables   📊

| Rule | Description                                                                    |
| ---- | ------------------------------------------------------------------------------ |
| L-1  | **No vertical lines** — use spacing and `booktabs` instead.                    |
| L-2  | **Full width** — all tables should span `\textwidth`.                          |
| L-3  | Use `tabularx`, `array`, or `booktabs` to automatically manage column spacing. |
| L-4  | **Caption on top**, followed by `\vspace{0.5em}` before the table body begins. |
| L-5  | Only use `\toprule`, `\midrule`, and `\bottomrule` for horizontal lines.       |
| L-6  | Use `@{}` in column templates to remove outer padding (e.g., `@{} l X @{}`).   |

---

### ✅ Recommended Table Template (Minimal, Beautiful, Aligned)

```latex
\usepackage{tabularx, booktabs}
\newcolumntype{L}[1]{>{\raggedright\arraybackslash}p{#1}}
% tabularx spans \textwidth, and L{6.4cm}/L{5.2cm} balance
% content beautifully
\begin{table}[h]
\centering
\begin{tabularx}{\textwidth}{@{}lL{6.4cm}L{5.2cm}@{}}
\toprule
\textbf{Symbol} & \textbf{Meaning} & \textbf{Type} \\
\midrule
$p_t$ & Log return at time $t$ &
Input series \\

$\Delta p_t$ & First-order difference  
($p_t - p_{t-1}$) &
Computable \\

$\gamma$ & Coefficient for trend reversion  
used in ADF regression &
To be fitted \\

$p$-value & Result of $t$-test on $\gamma$  
testing for unit root &
Output metric \\
\bottomrule
\end{tabularx}
\caption{Stationarity test variables and their roles}
\end{table}
```

---

## 6  File-Specific Precedence   📁

> *Always honor the most recently uploaded file of any given name.*
> Identical filenames do not imply identical content.
> See G-6.

---

### End of RULESET.md (2025-05-23)