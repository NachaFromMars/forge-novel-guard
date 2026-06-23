# forge-novel-guard — Quality gate for AI novel forging

> Battle-tested quality guard distilled from 70+ chapters of novel-forging experience. Automated verify scripts catch prose problems, broken EPUBs, and bad Telegram deliveries before they ship.

[![OpenClaw Skill](https://img.shields.io/badge/OpenClaw-Skill-blueviolet)](https://github.com/NachaFromMars)

## Overview
forge-novel-guard codifies the quality lessons from forging 70+ novel chapters into a reusable gate. Three verification scripts cover the main failure modes of AI-assisted writing: prose quality issues, EPUB structure problems, and Telegram file delivery failures. An activation table tells you exactly which section and script to run at each step of the forge workflow.

## Features
| Script | Checks |
|---|---|
| `verify-prose.py` | English content, markdown leaks, em dash, AI trace patterns, pronouns |
| `verify-epub.py` | EPUB structural validity |
| `verify-send.py` | Telegram file delivery correctness |

**Activation table:**
- Forge new chapter → Section 7 + verify after each beat
- Build EPUB → Section 1 + `verify-epub.py`
- Audit prose → `verify-prose.py`
- Telegram send → Section 3 + `verify-send.py`
- Sub-agent forge → Section 4 + inject rules into prompt

## Usage / Quick Start
```bash
python3 scripts/verify-prose.py chapter.md
python3 scripts/verify-epub.py book.epub
python3 scripts/verify-send.py
```

## Trigger Keywords (OpenClaw)
forge novel, forge chapter, viết chương, build epub, scan prose, verify epub, novel quality, AI trace, thẩm định chương

## Related Skills
- [novel-guardian](https://github.com/NachaFromMars/novel-guardian) — continuity & consistency checker
- [humanize](https://github.com/NachaFromMars/humanize) — strip AI writing patterns

---
Part of the [NachaFromMars](https://github.com/NachaFromMars) OpenClaw skill ecosystem.
