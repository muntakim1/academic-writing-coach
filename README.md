# Academic Writing Coach

**A custom Claude skill that coaches beginner researchers through writing their own journal draft, in one guided, time-boxed 2-hour session.**

Not a ghostwriter. A coach. The session produces two things: a complete, well-structured journal draft built from *your* research, and the transferable writing skill to do it yourself next time.

[![Claude Skill](https://img.shields.io/badge/Claude-Skill-d97757)](https://support.claude.com/en/articles/12512180-use-skills-in-claude)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

## Demo

https://github.com/muntakim1/academic-writing-coach/raw/main/academic-writing-coach-demo (1).mp4

*79-second demo with narration. If the embed does not play, the file is in root file.*

---

## Why this exists

Most beginner researchers do not struggle with research. They struggle with the writing around it:

- **Vague gap statements** ("little work has been done in this area...")
- **Novelty by adjective** ("we propose a novel and innovative method...")
- **Overclaimed results** ("our results prove that our model is the best")
- **Related work written as an annotated bibliography** instead of an argument
- **Contributions that float free of the stated gap**

These are not knowledge problems. They are craft problems, and craft can be taught systematically. This skill encodes that teaching into a repeatable coaching session.

## How the session works

The skill runs a structured, time-boxed session. The coach announces each phase, keeps the clock, and compresses later phases if you run long.

| Phase | Focus | Time |
|---|---|---|
| 0 | **Intake**: topic, findings, target venue, output format | ~10 min |
| 1 | **Framing**: motivation funnel, problem statement, gap classification | ~15 min |
| 2 | **Contribution and novelty**: contribution bullets, gap-contribution lock, positioning | ~20 min |
| 3 | **Story skeleton**: full outline plus a literature grounding map | ~20 min |
| 4 | **Annotated drafting**: every section, with `[COACH: ...]` notes explaining the craft | ~35 min |
| 5 | **Polish and audit**: language pass, 18-point quality checklist, final file | ~20 min |

Each phase includes one micro-exercise: you attempt a sentence or paragraph before the coach shows its version, then you compare. That is where the learning sticks.

### What it teaches

- **Research framing**: the CARS model, a five-type gap taxonomy, the motivation funnel
- **Contribution and novelty**: four contribution formulas with a quality bar, novelty positioning patterns, and the anti-patterns to avoid
- **Literature grounding**: related work as a thematic funnel where every theme ends pointing at your gap
- **First-class academic English**: a hedging ladder that calibrates claims to evidence, vocabulary upgrades, a filler blacklist, old-to-new paragraph flow, tense conventions, and common L2-writer error patterns

## Design principles

**1. It never fabricates.** No invented numbers, no hallucinated citations, no plausible-sounding filler. Unknown references become `[REF: description of needed source]` placeholders. Missing results become `[RESULT NEEDED: ...]` flags. You fill them from real work; the final audit counts and lists every one.

**2. It coaches instead of ghostwriting.** Content is elicited from you before anything is drafted. Drafted sections carry annotations explaining why each sentence works. The session closes with a personalized summary of your specific writing weaknesses, with before/after pairs from your own paper.

**3. It is honest about scope.** The output is a strong, complete draft, not a submission-ready manuscript. Anyone promising a publication-ready paper in 2 hours is selling something. The skill ends with an explicit handoff list: verify every reference, fill every result placeholder, re-check every novelty claim against a fresh literature search, and get a supervisor or co-author review before submission.

## What is inside

```
academic-writing-coach/
├── SKILL.md                        # The session workflow and coaching principles
├── references/
│   ├── rhetorical-moves.md         # CARS, gap taxonomy, contribution and novelty patterns
│   ├── language-toolkit.md         # Hedging ladder, vocabulary, sentence craft, error patterns
│   ├── section-templates.md        # Per-section structures with annotated examples (IMRaD)
│   └── quality-checklist.md        # The final 18-point audit
├── demo/
│   └── academic-writing-coach-demo.mp4
└── README.md
```

The skill uses progressive disclosure: Claude loads only the reference file each phase needs, keeping the context footprint small.

## Installation

### Claude.ai (web and desktop)

1. Download this repository as a ZIP, or zip the `academic-writing-coach/` folder (the ZIP must contain the folder with `SKILL.md` inside).
2. In Claude, go to **Customize > Skills**, click **+**, and upload the ZIP.
3. Make sure **Code execution and file creation** is enabled under **Settings > Capabilities**.
4. Toggle the skill on. Uploaded skills are private to your account.

### Claude Code

```bash
git clone https://github.com/muntakim1/academic-writing-coach.git
cp -r academic-writing-coach ~/.claude/skills/        # personal, all projects
# or: cp -r academic-writing-coach .claude/skills/    # project-scoped
```

Start a new session; the skill is detected automatically. Run `/skills` to confirm it loaded.

## Usage

Start a conversation with something like:

> "Help me write my paper on few-shot intrusion detection. I have results but my drafts keep getting criticized."

or simply:

> "Run an academic writing coaching session."

**Bring to the session:** your topic, your methods and key results (rough notes, bullet points, or result tables are fine), your target venue if you know it, and your preferred output format (Word or LaTeX).

**Leave with:** a complete annotated draft, an audit report of what passed and what you still must fix, and a personal skills summary.

## What this skill will not do

- Invent experimental results, datasets, or citations, under any framing
- Write a paper from nothing (no results means a framing draft, stated honestly)
- Replace supervisor review, co-author input, or your own verification pass
- Guarantee acceptance anywhere

## Author

**Muntakimur Rahaman**, Graduate Research Assistant, Multimedia University (Cyberjaya, Malaysia). Research in ML for O-RAN, few-shot meta-learning for encrypted traffic classification, and post-quantum cryptography.

Portfolio: [muntakim.xyz](https://muntakim.xyz) · GitHub: [@muntakim1](https://github.com/muntakim1)

## License

MIT. Use it, adapt it, teach with it. If it helps your students write better papers, that is the point.
