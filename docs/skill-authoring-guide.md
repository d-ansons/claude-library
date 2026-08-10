# Skill authoring guide

Strict rules for every skill in this repo. Follow this document when writing a new skill or editing an existing one. Sources: [Claude Code skills docs](https://code.claude.com/docs/en/skills) and the [Agent Skills best-practices spec](https://agentskills.io/skill-creation/best-practices).

## Why this matters

Once a skill triggers, its whole `SKILL.md` body loads into context and stays there for the rest of the session, competing for the model's attention with everything else. A vague or bloated skill doesn't just waste tokens — it actively degrades output on other tasks. Every rule below exists to keep a skill's signal-to-noise ratio high.

## 1. Frontmatter

- Only `description` is required in practice. Put the **key use case first** — it gets truncated at 1,536 characters in the skill listing.
- Write `description` as: what it does + when to use it, including concrete trigger phrases ("Use when the user asks to summarise/explain/give an overview of...").
- Set `disable-model-invocation: true` only for skills with side effects the user must control (deploys, sends, commits). Leave it unset for skills that should trigger automatically from conversation.
- Don't add fields you don't need (`allowed-tools`, `context: fork`, `model`, etc.) unless the skill actually requires them.

**Bad:** `description: Summarises things`
**Good:** `description: Summarise a technical topic using a fixed structure. Use when the user asks to summarise, explain, or give an overview of a technical topic, concept, tool, or technology.`

## 2. Length and progressive disclosure

- Keep `SKILL.md` under 500 lines / ~5,000 tokens. It should contain only what's needed on every run.
- Move detailed reference material, large examples, or scripts to separate files (`reference.md`, `examples/`, `scripts/`) and link to them from `SKILL.md`, stating **when** to load each one (e.g. "see `reference.md` if X happens"), not just "see reference.md for details".
- A skill that ships exactly one skill can skip the `skills/` nesting and put `SKILL.md` at the plugin root — but for anything that may grow supporting files, keep the `skills/<name>/SKILL.md` layout.

## 3. Content: add what the agent lacks, cut what it already knows

- Don't explain concepts the model already understands (what a PDF is, how HTTP works). Jump straight to the project- or domain-specific instruction.
- Test every line against: "Would the agent get this wrong without this instruction?" If no, cut it.
- Prefer concise, stepwise guidance with one working example over exhaustive documentation covering every edge case.

## 4. Scope skills as coherent units

- A skill should cover one coherent unit of work, like a well-scoped function. Too narrow → multiple skills fighting to load for one task. Too broad → hard to trigger precisely and hard to keep coherent.

## 5. Calibrate prescriptiveness to fragility

- **Give freedom** (and explain *why*) when multiple approaches are valid and the task tolerates variation.
- **Be prescriptive** ("run exactly this command, do not add flags") when the operation is fragile or order-dependent.
- **Provide one default**, not a menu of equally-weighted options, when several tools/approaches could work. Mention the alternative briefly as an escape hatch.

## 6. Favor procedures over declarations

A skill should teach *how to approach* a class of problems, not give the answer to one specific instance. Write the repeatable method, not a one-off worked answer.

## 7. Useful patterns (use what fits, not all of them)

- **Gotchas section**: non-obvious, environment-specific facts that defy reasonable assumptions (not generic advice like "handle errors well"). This is usually the highest-value content in a skill.
- **Output templates**: when output must follow a specific structure, give a literal markdown template — agents pattern-match against concrete structure far more reliably than prose descriptions of format.
- **Checklists**: for multi-step workflows with dependencies, so steps aren't skipped.
- **Validation loops**: do the work → run/apply a validator → fix → repeat until it passes.
- **Bundled scripts**: if the agent would reinvent the same logic every run (parsing, chart generation), write it once as a script in `scripts/` instead of prose instructions.

## 8. Never fabricate

If a skill asks for links, citations, versions, or facts, the instructions must tell Claude to only include what it can verify (e.g. via search) and to say "not verified" rather than guess. Treat hallucinated specifics as a correctness bug in the skill, not an acceptable trade-off.

## 9. Evaluate before trusting

A skill triggering is not evidence it works. Before relying on a new/changed skill:
1. Write 2-3 realistic prompts that should trigger it, and 1-2 that shouldn't.
2. Run each in a fresh session with the skill enabled and disabled, and compare.
3. Iterate on `description` if it triggers on the wrong prompts, and on the body if the output is wrong when it does trigger.

## Checklist before shipping a skill

- [ ] `description` leads with the core use case and lists trigger phrases
- [ ] Body is procedural, not a wall of generic advice
- [ ] Under 500 lines; anything longer moved to supporting files with a "load this when X" pointer
- [ ] No content the model already knows without the skill
- [ ] One default approach given, not a menu, where choices exist
- [ ] Gotchas (if any) are inline in `SKILL.md`, not buried in a reference file
- [ ] Output format given as a literal template if format matters
- [ ] Any instruction to cite/link/quote external facts includes a no-fabrication rule
- [ ] Tested with a couple of should-trigger and should-not-trigger prompts
