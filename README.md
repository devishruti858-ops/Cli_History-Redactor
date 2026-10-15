# CLI History Sanitizer & R&D Dashboard

A high-performance security tool and interactive R&D dashboard built entirely in Python (Standard Library only) designed to scan terminal shell histories (`.bash_history`, `.zsh_history`), detect accidental credential leaks, redact secrets securely, and generate comprehensive forensic audit reports.

---

## Key Features

* **Dual Detection Engine**: Combines **18 curated Regular Expression rules** (covering AWS keys, GitHub tokens, OpenAI/Anthropic keys, Stripe keys, JWTs, private SSH key blocks, and connection URLs) with a **Shannon Entropy analysis heuristic** ($H \ge 4.3$ bits/char) to catch unpatterned or zero-day secret tokens.
* **Interactive Offline R&D Dashboard**: A built-in local web server (`--dashboard`) that opens a fully responsive browser interface with **14 distinct visual themes** (Solarized Dark, Dracula, Nord, Cyberpunk, Synthwave, Matrix, etc.).
* **Built-in 15-Slide Review Deck**: An interactive technical presentation deck embedded directly in the dashboard UI with speaker notes and keyboard slide navigation (`ArrowLeft`, `ArrowRight`).
* **Flexible Redaction Styles**: Choose between `placeholder` (`[REDACTED:TAG]`), `mask` (`********`), `partial` (`abcd****`), or `hash` (`[TAG:HASH]`).
* **CI/CD Automation Ready**: Headless CLI mode supports automated pre-commit and pipeline scans, exiting with code `1` upon critical secret detection.

---

## Installation & Requirements

* **Python 3.x** (Standard Library only — **Zero external package dependencies** required).

---

## How to Run

### 1. Launch the Interactive R&D Dashboard (Recommended)
Starts a local offline web server on port `8080` and opens the dashboard automatically in your default browser:
```bash
python3 appproject.py --dashboard
