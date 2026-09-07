---
description: Turn rough notes about a work project or achievement (e.g. a delivered project, or a non-delivery win like selling follow-on work to a client) into a structured case study (timeline placing it in the user's career, context, outcome, an experience-value rating out of 10, key skills, CV bullet points each rated for CV relevance out of 10, a STAR-format interview story plus sample answers to likely interview questions, domain tags, and things to learn) via an interview loop that writes a draft file immediately and updates it after every round of targeted follow-up questions until the picture is solid. Probes for depth by asking about tool-specific decisions the user likely made but didn't mention (e.g. Import vs. DirectQuery for a Power BI report). Links related case studies under the same ongoing client engagement, and screens for confidential/sensitive details before finalizing. Use when the user wants to document a past project, an achievement like winning or expanding client work, build a case study entry, write up a project retrospective for a portfolio/CV repo, prep interview answers from past work, or says things like "let's write up this project" or "add a case study for X".
---

# Case Study Builder

Build one case study per invocation by looping between the user's notes and targeted questions — writing a real draft file after the first round and updating it after every subsequent round, per Drafting As You Go below. The file should always reflect the current state of the conversation; never hold everything in your head and produce a single big write-up only at the end.

## Procedure

1. **Take the initial notes.** Read whatever the user gives you (a few sentences, a brain dump, a Slack message, whatever). Don't ask for a "properly formatted" input first.

2. **Determine the case study type** — Delivery or Achievement (see Case Study Types below). If it's obvious from the notes, state your read and let the user correct it rather than asking outright; only ask directly if it's genuinely ambiguous.

3. **Check notes against the completeness checklist** for that type (below). Anything missing or vague is a gap.

4. **Write the draft file now**, before asking anything, per Drafting As You Go below — filled with whatever is already known, clearly marked placeholders for the rest. Tell the user the file path.

5. **Ask about gaps in one batched message**, not one question at a time. Group related questions together, be concrete about what's missing, and reference specifics the user already gave you rather than asking generically ("What was the impact?" is weak; "You mentioned the migration cut deploy time — do you have a rough before/after number, even approximate?" is strong). Include the parent-engagement, timeline, and depth-probing questions (below) in this same first round.

6. **Update the draft file with the new answers**, then re-check the checklist for what's still missing. Keep looping — ask, update the file, re-check — until every checklist item is either filled or explicitly marked as not applicable/not known by the user. Most case studies converge in 2-4 rounds — if you're still asking after that, you're probably over-interrogating; ask what's left in one final pass and move on with "Not specified" for anything still missing.

7. **Never fabricate.** Do not invent metrics, outcomes, tools, team sizes, or timeframes the user hasn't stated. If something is missing after being asked, write "Not specified" in the file rather than guessing a plausible-sounding number or detail.

8. **Before finishing, do one final check** covering sensitivity and tags together (see Confidentiality Screening and Tags below) — bundle both into the same message so this doesn't add an extra round on its own.

9. **Complete the draft** — fill in the rating, CV bullets, STAR story, and interview Q&A (which need the full picture to be worth generating), replace any remaining placeholders with "Not specified", and update the file one last time. Apply the rating rubrics, CV bullet rules, and STAR guidance below.

## Drafting as you go

The case study lives in a real file from the first round onward, not just in conversation — the user should be able to watch it fill in and can hand-edit it between rounds.

- **Where to save it**: if the current directory (or a parent-engagement match you found) shows an existing case-studies location or naming convention, follow it. Otherwise create `<slug-of-project-name>.md` in the current directory and tell the user the path so they can redirect you if it's wrong.
- **First write**: use [template.md](template.md)'s structure, filling every field you already know from the initial notes. For anything you don't know yet, write the literal placeholder `*(pending)*` — don't guess and don't leave the section heading empty.
- **Every round after that**: re-read the file first — the user may have edited it directly — then use Edit to update only the sections affected by the new answers. Don't regenerate the whole file from scratch each round; that discards anything the user hand-edited.
- **Generated sections** (Experience Value, CV Bullet Points, Key Skills, Interview Story, Interview Questions & Sample Answers) stay `*(pending)*` until step 9, since they need the full picture to be worth writing — don't half-generate them early and then rewrite them later.
- **Finishing**: by the end, no `*(pending)*` markers should remain — anything genuinely never answered becomes "Not specified" instead.

## Case study types

Not everything worth documenting is a build/ship narrative. Pick whichever fits, and confirm your read with the user rather than silently assuming:

- **Delivery** (default): the user built, shipped, or led a concrete piece of work — a project, feature, migration, process rollout.
- **Achievement**: a discrete win without a build narrative — selling or expanding work with a client, a renewal, an award, a promotion, forming a partnership. These are just as CV-worthy, especially for client-facing/consulting roles, but don't force a technical narrative onto them.

The template shape is the same for both — Achievement entries just treat **Tools & Technologies** as optional (mark "N/A" if nothing meaningful applies) and write **What I Did** around the actions that produced the win (the pitch, relationship-building, timing, groundwork from prior work) instead of a technical build. Always include the type itself (`delivery` or `achievement`) as one of the Tags so entries can be filtered by type later.

## Completeness checklist

A case study is ready to write once you can answer all of these from the conversation. Items marked (Delivery only) or (Achievement only) apply just to that type — everything else applies to both.

- **Context**: what was the project/achievement, what was the user's role, and for what team or company (or "personal project" if not work-affiliated).
- **Timeline**: concrete dates and where this sits in the user's career — see Timeline below.
- **Parent engagement**: is this part of a larger ongoing client engagement or program that already has (or will have) other separate case studies, or is it standalone? See Parent Engagement & Related Case Studies below — don't assume linkage just because the client matches; confirm it.
- **Problem/goal**: what was the project trying to achieve or what problem did it solve. (Delivery only)
- **Actions**: what did the user actually do — decisions made, approach taken, not just "worked on X." (Delivery only)
- **Tools/tech**: specific tools, languages, frameworks, or methods used. (Delivery only)
- **How it happened** (Achievement only): what the user specifically did to produce the win — the pitch, the relationship groundwork, the timing.
- **Outcome**: what happened as a result — ideally a number or concrete change (revenue/scope for an Achievement), but a qualitative outcome is acceptable if the user has no metric.
- **Challenges**: at least one non-trivial obstacle and how it was handled. This is usually the richest source of skills and CV material — dig for it if the notes don't mention one. (Optional for Achievement entries if none applies.)
- **Depth**: for every specific tool/technology named, at least one likely-but-unmentioned decision or detail has been asked about — see Probing for Depth below. (Delivery only)

## Probing for depth

Users routinely under-report what they actually did because the details felt too routine to mention. For every specific tool, technology, or methodology named in the notes, think like a practitioner of that tool: what decision or sub-task does anyone using it in this way almost certainly have to handle? Ask about that directly, by name, instead of a generic "tell me more" — naming the specific thing signals you understand the tool and makes it easy for the user to answer in one line.

Examples of the pattern (not a fixed list — apply the same reasoning to whatever's actually named):
- "Power BI report" → ask whether it used Import or DirectQuery mode, and whether there was any real data modeling/DAX involved.
- "Deployed on Kubernetes" → ask about how they handled resource requests/limits, ingress/service exposure, or secrets/config.
- "Led a migration/cutover" → ask what the rollback plan or fallback strategy was.
- "Built a data pipeline" → ask about the orchestration/scheduling approach and how failures or retries were handled.

Guardrails:
- Ask about a decision only when the way they described using the tool makes it genuinely likely they encountered it — don't interrogate every possible feature of a tool.
- Fold these into the same batched question round as everything else (see the main procedure) — this is not a separate round.
- Cap it: 1-2 depth questions per tool actually named that seems likely to reveal something CV/skill-worthy, prioritizing the tool(s) most central to the project.
- If the user says "I don't remember" or "that wasn't something I decided," drop it — this is meant to surface real depth, not test their memory.

## Timeline

Each case study should be placeable on a single lineage across the user's whole career, so ask for calendar precision here even though you'd accept looser answers elsewhere.

- **Dates**: get at least month/year for when the project started and ended (or "Ongoing"). "A few months ago" or "last year" isn't enough — push once for the actual month/year, but accept an approximate one ("early 2023, not sure of the exact month") rather than blocking on it.
- **Role at the time**: the job title and employer the user held when this happened — this may repeat what's in Context, that's fine, Timeline needs to stand on its own.
- **Sequence note** (optional but valuable): how this fits relative to other career milestones the user mentions — e.g. "6 months into this role, 2 months before promotion to Senior," or "second project in the Acme engagement, after the platform migration." Only include this if the user actually says something placing it in sequence; don't invent a position.

## Parent engagement & related case studies

Some work happens inside a longer-running client engagement (e.g. embedded with a client's team, delivering separate sub-projects month to month) where individual case studies are genuinely related to each other — but not always; don't assume every entry for the same client is linked.

- Ask whether this entry belongs to a broader ongoing engagement. If yes, get (or agree on) one consistent name for it (e.g. "Acme Platform Engagement") and reuse that exact name across every case study under it — consistent naming is what makes entries findable later, there's no separate index file to maintain.
- If other case study files are visible in the current working directory, search them (grep for the engagement name or client name) for matches and list them under **Related Case Studies** as relative markdown links.
- When you find a match, ask the user whether to also add a reciprocal link in that older file — don't edit files outside the current one without asking first.
- If this entry is standalone, just write "Standalone" and move on — don't push for a parent engagement that isn't there.

## Confidentiality screening

Case study repos are often kept as public portfolios, so before writing, scan the gathered notes for anything that looks like it shouldn't be published verbatim: real client/customer names, employer-internal metrics not otherwise public (revenue, user counts, salaries), proprietary internal tool or codebase names, or anything the user has flagged as under NDA.

- Flag what you found in plain terms and ask how to handle each item — keep as-is, generalize (e.g. "a Fortune 500 retail client" instead of the real name, "a significant reduction" instead of an exact percentage), or drop entirely.
- If the user doesn't respond to this or says they're not sure, default to generalizing rather than keeping specifics — the safer failure mode for a document that might go public.
- Don't over-flag: the user's own employer name, their own role, and technology/tool names (React, Kubernetes, etc.) are normally fine and not worth asking about.

## Tags

Propose 2-4 short, lowercase, kebab-case tags based on the skills and domain discussed (e.g. `backend`, `leadership`, `data-migration`, `client-facing`). Show the proposed tags in the same final message as the confidentiality check and let the user accept or edit them in one reply — don't turn this into its own question round.

## Rating rubrics

Apply these consistently across every case study so ratings stay comparable to each other over time.

**Experience Value (out of 10)** — how much this project grew the user's skills/experience:
- 1-3: routine work, well within existing skills, little new learned.
- 4-6: solid work with some new tools/responsibility, moderate stretch.
- 7-8: significant stretch — new domain, higher ownership, or notable complexity.
- 9-10: transformative — led something ambiguous/high-stakes, or a big jump in scope/seniority.

**CV Relevance (out of 10, per bullet)** — how much that specific bullet would strengthen a CV for the roles the user is likely targeting:
- 1-3: too niche, internal-only, or generic to be worth including.
- 4-6: decent supporting bullet, useful as one of several.
- 7-8: strong, quantifiable, relevant to common job requirements.
- 9-10: a standout, headline-worthy bullet.

If you don't know what roles the user is targeting, ask once during the question rounds rather than guessing — it changes which bullets rate highly.

## Writing CV bullet points

- Format: strong action verb + what was done + quantified or concrete result, e.g. "Redesigned the checkout flow, cutting cart abandonment by 18%."
- Only quantify with numbers the user actually gave you. If no number exists, use a concrete qualitative result instead of a vague one ("shipped to production and adopted by 3 teams" beats "improved the system").
- Produce 2-5 bullets per case study — don't pad with weak restatements of the same accomplishment.

## Writing the STAR interview story

This section turns the case study into something the user can recite in a behavioral interview ("Tell me about a time you..."). Build it from information already gathered — don't ask new questions for it.

- **Situation**: 1-2 sentences of context (from the Context/problem-goal answers).
- **Task**: 1 sentence — what the user specifically needed to achieve or was responsible for.
- **Action**: 2-4 sentences — what they actually did, in first person, past tense, emphasizing their own decisions (not the team's or the company's).
- **Result**: 1-2 sentences — the outcome, using the same numbers/facts as the Outcome section (after confidentiality screening), plus a brief note on what they learned if it strengthens the story.
- Keep the whole thing tight enough to say out loud in under a minute (roughly 100-150 words total).

## Writing interview questions & sample answers

This section shows the versatility of one piece of experience — the same story can answer several different interview questions, each with a different emphasis. Derive everything here from facts already gathered (including the STAR story) — don't ask new questions and don't invent details to make an answer sound punchier.

- Pick 2-4 real interview questions this specific experience would genuinely answer well, matched to what's actually strong in the story. Draw from categories like: a technical/business challenge overcome, influencing without authority or cross-team disagreement, a project the user is proud of, learning something quickly, identifying an opportunity (natural fit for an Achievement entry), or a decision made with incomplete information.
- Don't force categories that don't fit — a purely technical delivery with no people-friction shouldn't get an "handling conflict" question just to fill a slot.
- For each question, write a sample answer that reframes the same underlying facts with the emphasis that question is actually probing — don't paste the same STAR block verbatim under every question.
- Keep each answer compressed and spoken-style, first person, roughly 80-120 words.

## Gotchas

- A well-written case study is not the same as a flattering one — if the user says a project was messy or the outcome was mediocre, reflect that honestly in the rating and outcome section rather than smoothing it over.
- Skills and "things to learn" are different: Key Skills Covered is what the user already demonstrated; Things to Learn is what they were exposed to but haven't mastered (tools/concepts worth following up on).
- Don't restart the whole loop if the user later edits one detail — just update the affected section(s) of the already-written case study.
- Run the confidentiality screening before writing the STAR story, sample interview answers, and CV bullets too, not just the main body — a sanitized Outcome section paired with unsanitized answers elsewhere defeats the point.
- An Achievement entry still gets a full Experience Value rating, CV bullets, and STAR story — "sold two follow-on projects" is legitimate CV material, don't downgrade it just because it lacks a technical build narrative.
- Parent-engagement linking is opt-in per entry, not automatic — two case studies for the same client are only "related" if the user says so.
- Always re-read the draft file before editing it in a later round — don't assume it still matches what you last wrote, the user can edit it between rounds.
- Timeline dates matter more than they might seem: they're what lets the user reconstruct a full career lineage across every case study in the repo, so don't let vague relative time ("recently," "a while back") slide through unchallenged the way you might for other soft details.
