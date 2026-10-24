# Disfluency & Repair Grammar

> **Tri-Platform Agent Skill** for Claude Desktop / Code, Grok CLI, and Google Antigravity / Gemini.  
> Speech Disfluency, Filler Words, and Repair Modeling — Models conversational speech disfluencies, false starts, mid-word cutoffs, filler words, repetitions, and speech repairs for human-like natural voice synthesis.

---

## Overview

`disfluency-repair-grammar` provides standardized capabilities across conversational AI platforms:
- Standard 4-phase disfluency taxonomy (reparandum, interruption point, editing phase, repair).
- Quantitative filler word probability distributions tailored to speaker age and register.
- Glottal cutoff acoustics, word fragmentation, and prolongation parameterization.
- Machine-readable disfluency_grammar.json output specification.
- SSML break and pitch modification tag generation.
- Tri-platform NTFS junctions connecting Claude, Grok, and Antigravity.
- Standard documentation suite: SKILL.md, HOW_TO_USE.txt, IMPLEMENTATION_PLAN.md, and README.md.

---

## Tri-Platform Architecture

Zero duplicate code across platforms. Canonical source resides in `.agents`:
- **Canonical Source**: `C:\Users\<you>\.agents\skills\disfluency-repair-grammar`
- **Claude**: `C:\Users\<you>\.claude\skills\disfluency-repair-grammar` (NTFS Junction)
- **Grok**: `C:\Users\<you>\.grok\skills\disfluency-repair-grammar` (NTFS Junction)
- **Antigravity**: `C:\Users\<you>\.gemini\config\skills\disfluency-repair-grammar` (NTFS Junction)

---

## Documentation Suite

- [`HOW_TO_USE.txt`](HOW_TO_USE.txt): Standardized user guide and prompt templates.
- [`IMPLEMENTATION_PLAN.md`](IMPLEMENTATION_PLAN.md): Feature checklist and roadmap.
- [`App Changes Tracker.html`](App%20Changes%20Tracker.html): Interactive visual version log.
- [`SKILL.md`](SKILL.md): Agent system instructions and triggers.
