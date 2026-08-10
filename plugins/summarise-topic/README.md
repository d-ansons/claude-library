# summarise-topic

A Claude Code skill that makes Claude always return the same structure when asked to summarise a technical topic.

Always outputs four sections, in order: **Overview** (4-5 paragraphs), **Examples**, **Useful Articles** (verified links only), **Best Practices** (good vs bad per practice, each explained). Adds a fifth, **Practical Suggestion**, only when a genuinely hands-on task (a couple of hours or less) makes sense for the topic.

Written against the rules in [docs/skill-authoring-guide.md](../../docs/skill-authoring-guide.md).

## Local testing

```bash
claude --plugin-dir ./plugins/summarise-topic
```

Then try `/summarise-topic:summarise-topic` or let it trigger automatically when you ask Claude to summarise a technical topic.
