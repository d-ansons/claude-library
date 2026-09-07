# case-study

A Claude Code skill for building work project case studies (for a personal portfolio/CV repo) through an interview loop instead of a single-shot write-up.

Give it rough notes about a project or achievement (a delivery, or a non-delivery win like selling follow-on work to a client); it writes a draft file immediately with `*(pending)*` placeholders, then checks against a completeness checklist and asks batched, targeted follow-up questions round by round, updating the same file in place after each answer — never fabricating missing details, and re-reading the file each round in case you've hand-edited it. It also probes for depth: for every specific tool named (e.g. "Power BI report"), it asks about the decision a practitioner almost certainly made but didn't mention (Import vs. DirectQuery mode), instead of settling for surface-level tool names. If the entry is part of a longer-running client engagement, it links it to other case studies sharing that engagement name. Before finishing, it screens the gathered details for anything that looks confidential (client names, internal metrics, NDA-covered specifics) and offers to generalize them, since case study repos are often kept as public portfolios. The finished file covers:

- A **Timeline** (calendar dates, role at the time, and how it sequences against other career milestones) so entries can be strung into a full career lineage
- Tags (including type — delivery/achievement), parent engagement links, context, what was done, tools used, and outcome
- **Experience Value** rating out of 10 (rubric-based, comparable across case studies)
- **Key Skills Covered**
- **CV Bullet Points**, each with a **CV Relevance** rating out of 10
- **Things to Learn** (tools and concepts worth following up on)
- An **Interview Story (STAR)** section plus **sample answers to likely interview questions**, built from the same vetted details

Written against the rules in [docs/skill-authoring-guide.md](../../docs/skill-authoring-guide.md).

## Local testing

```bash
claude --plugin-dir ./plugins/case-study
```

Then try `/case-study:case-study` or let it trigger automatically when you ask Claude to write up or document a project.
