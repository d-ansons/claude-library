# claude-library

A personal marketplace of Claude Code plugins (skills and agents) for my own workflow.

## Structure

```
.
├── .claude-plugin/
│   └── marketplace.json   # marketplace catalog — lists every plugin below
└── plugins/
    └── <plugin-name>/
        ├── .claude-plugin/
        │   └── plugin.json # plugin manifest (name, description, version)
        ├── skills/          # Agent Skills (SKILL.md per folder)
        ├── agents/          # subagent definitions (optional)
        └── README.md
```

Each plugin lives in its own directory under `plugins/` and is self-contained. The root `.claude-plugin/marketplace.json` is the catalog that ties them together so they can be installed with `/plugin install <plugin>@claude-library`.

## Plugins

| Plugin | Description |
| --- | --- |
| [summarise-topic](plugins/summarise-topic) | Makes Claude always return the same structure when summarising a technical topic. |
| [case-study](plugins/case-study) | Builds a work project case study through an interview loop that drafts and updates a file live, probes for tool-specific depth, and fills a career timeline, ratings, CV bullet points, a STAR interview story with sample Q&A, and tags. |

## Using this marketplace locally

Register it from a local checkout:

```bash
claude plugin marketplace add /path/to/claude-library
claude plugin install summarise-topic@claude-library
```

Or once pushed to GitHub:

```bash
/plugin marketplace add d-ansons/claude-library
```

## Developing a plugin

Test a plugin directly without installing it:

```bash
claude --plugin-dir ./plugins/summarise-topic
```

## Adding a new plugin

1. Create `plugins/<name>/.claude-plugin/plugin.json` with `name`, `description`, `version`.
2. Add its skill(s) under `plugins/<name>/skills/<skill-name>/SKILL.md` (or `agents/` for subagents).
3. Add an entry to the `plugins` array in `.claude-plugin/marketplace.json`.
4. Test locally with `--plugin-dir`, then commit.
