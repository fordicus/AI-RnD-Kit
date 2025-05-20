# 🛠️ AI R&D Kit

This repository provides utilities and rules for working collaboratively with AI agents (like ChatGPT) for research and development purposes. It includes file system visualization tools and coding standards designed for clarity, reproducibility, and automation.

---

### 📐 Ruleset Overview

We apply a unified ruleset (`RULESET.md`) for programming and documentation,  
which is updated and expanded as needed.  
These rules ensure consistency when collaborating with AI agents or humans.

### 🗂️ fs_to_html.py

A utility to convert the current project directory structure into an interactive HTML file (`REPO_STRUCT.html`), respecting `.gitignore`-style rules.

**How to run:**

```bash
python fs_to_html.py
```

---

## Excluded Scope

### Web Crawling

Fully crawling both the structure and content of modern websites is technically challenging due to the following reasons:

| Technology Feature              | Description                                                       | Crawling Difficulty                           |
| ------------------------------- | ----------------------------------------------------------------- | --------------------------------------------- |
| **SPA (Single Page App)**       | Content is dynamically injected via JavaScript (e.g., React, Vue) | 🟥 Very High                                  |
| **iframe**                      | Content is embedded from external URLs                            | 🟧 Moderate (security restrictions may apply) |
| **Shadow DOM**                  | Semantically hidden DOM trees not easily accessible               | 🟨 High (not reachable via `querySelector`)   |
| **Ajax/XHR/Fetch**              | Content is loaded asynchronously via API calls                    | 🟧 Moderate                                   |
| **Lazy Load / Infinite Scroll** | Content loads only when in viewport                              | 🟧 Moderate to High                           |

## 🛡️ License

This project is licensed under the  
✍️ [Creative Commons Attribution-NonCommercial 4.0 International License – Legal Code](https://creativecommons.org/licenses/by-nc/4.0/legalcode).  
🚫💰 Commercial use is prohibited.  
✨🛠️ Adaptation is permitted with attribution.  
⚠️ No warranty is provided.

[![License: CC BY-NC 4.0](https://licensebuttons.net/l/by-nc/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc/4.0/legalcode)
