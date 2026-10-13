# linkedin-profile-auditor

A Claude Skill that scores a LinkedIn profile out of 50 and rewrites every section around the outcome the person actually wants.

## What it does

A LinkedIn profile has two jobs: get *found* by a search, then *convince* the human who opens it. Most profiles do neither — they're a resume in the wrong format, written for a career the person already left.

This skill starts by naming the outcome, because everything on the profile should point at one:

1. **Establishes the goal first** — inbound recruiter interest for a specific title, a pivot, client leads, or founder credibility
2. **Scores out of 50** section by section, with sub-scores and reasons
3. **Ranks the three highest-leverage fixes** (usually the headline and the first two lines of About — they're what appear in search results and notifications)
4. **Rewrites every section** in full, in the person's own voice

## The rubric

| Section | Points |
|---|---|
| Headline | 10 |
| About | 10 |
| Experience | 15 |
| Skills, keywords, and searchability | 8 |
| Proof and presentation | 7 |

## Install

**In Claude (web or desktop):**
1. Download `SKILL.md` from this repo.
2. Open Claude's **Settings**.
3. Find the **Skills** section (under Capabilities).
4. Choose **Upload skill** and select the file.

**In Claude Code:**
1. Open a terminal.
2. Run `mkdir -p ~/.claude/skills/linkedin-profile-auditor`
3. Copy `SKILL.md` into that folder.
4. Restart Claude Code.

## How to use it

Paste the profile text, upload the profile PDF export, or share a screenshot. Then:

- "Why am I not getting recruiter messages?"
- "Does my profile read right for a Senior Manager implementation role?"
- "I'm switching industries and my profile doesn't reflect it."
- "Rewrite my headline."

It asks for the target outcome before scoring, since the same profile scores very differently against different goals. Works for your own profile or for a candidate you're coaching — in the coaching case it adds a note on how to hand the feedback over.

## What you get back

```
## Score: NN/50 — one-line read
### Breakdown                 (sub-scores with reasons)
### Fix these three first     (ranked by impact)
### Rewritten profile
    Headline — 3–5 options with a pick
    About — full text
    Experience — rewritten role by role
    Skills & keywords — terms and placement
    Proof & presentation — action list
### What I need from you      (numbers left blank, not invented)
```

## Notes

- Everything written has to be defensible in an interview. Reframing what's genuinely there is fair; inflated titles, invented metrics, and implied scope are not.
- It reads the original for voice before rewriting. A spare technical writer doesn't get warmth they'd never use.

## Contents

```
linkedin-profile-auditor/
├── SKILL.md
└── README.md
```

## License

MIT
