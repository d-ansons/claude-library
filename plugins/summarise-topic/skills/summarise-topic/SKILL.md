---
description: Summarise a technical topic using a fixed structure (overview, examples, useful articles, best practices, plus an optional practical suggestion). Use when the user asks to summarise, explain, give an overview of, or "TL;DR" a technical topic, concept, tool, language, or technology.
---

# Summarise Topic

Always use sections 1-4 below, in order, for every technical topic summary. Do not add, remove, or reorder these four. If one is thin for this particular topic (e.g. no widely-known best practices exist), keep the heading and say so in one line rather than dropping it.

Section 5, Practical Suggestion, is the one exception: include it only when it genuinely applies (see its rule below), and omit the heading entirely when it doesn't — it's the only section allowed to be dropped outright.

## 1. Overview
- 4-5 paragraphs maximum, prose only, no bullet lists, no code.
- Cover: what it is, what problem it solves / why it exists, how it fits into the broader ecosystem, and its key characteristics or trade-offs.
- Written to build a correct mental model fast — not a full history or marketing pitch.

## 2. Examples
- If the topic is code, an API, a CLI, or a tool: give 1-3 short, runnable snippets in fenced code blocks with a language tag, each showing a typical/idiomatic usage.
- If the topic is not code (e.g. an architecture pattern, methodology, protocol): give a concrete worked scenario instead of code.
- Minimal and illustrative only — this is not a tutorial. Skip trivial "hello world" filler; show the part that's actually representative.

## 3. Useful Articles
- 3-6 links worth reading to go deeper, official docs/spec first, then high-quality independent explainers.
- One line per link: `[Title](url) — why it's worth reading`.
- **Never fabricate a URL.** Only include a link you can verify exists (use WebSearch/WebFetch if available and unsure). If you cannot verify enough good links, list fewer and say so — do not guess at a URL to fill the quota.

## 4. Best Practices
- 3-5 practices, each with a **Good** and a **Bad** example (code snippet if the topic is code, short concrete description otherwise).
- Prioritise non-obvious gotchas over generic advice. Reject anything you'd write for any topic ("write clean code", "handle errors properly") — it must be specific to this topic.
- Every Good and every Bad example needs 1-2 sentences explaining *why* it's good or bad (the concrete consequence — what breaks, what it costs, what it protects against). An example with no explanation is a bare assertion and is not acceptable output.

## 5. Practical Suggestion (optional — include only when it truly makes sense)
- Include this section only when there's a genuinely useful, hands-on task for the reader: a small coding challenge, a command to run and observe, a sandbox/lab to spin up, a tool to install and try. It must be completable in a couple of hours or less by someone learning the topic.
- If no such task exists for this topic — it's purely conceptual, organizational, or has nothing concrete to build or run — omit the section entirely (no heading, no placeholder note). Don't force one in just to fill the slot.
- When included, cover three things: the task itself (2-4 sentences), concrete steps (exact commands, or a minimal spec of what to build), and what success looks like (what you should observe or produce that tells you it worked).
- Keep it low-effort: no new accounts, no paid infrastructure, no toolchain beyond what's typically already installed — unless setting up a small local sandbox (e.g. via Docker) *is* the exercise.

## Output format

Before writing the summary, read [template.md](template.md) and fill its structure exactly — it defines the literal section layout and heading levels to output.
