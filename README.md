# Data Visualization Playbook

An [Agent Skill](https://code.claude.com/docs/en/skills) for data storytelling: a working
method plus ~600 prescriptive rules for choosing, building, and reviewing data
visualizations. Written for an LLM agent — every line is a rule or a procedure, not prose —
and source- and medium-agnostic: it applies whether the output is plotting code, inline
SVG, a BI dashboard, or an exported image.

It covers two jobs with one shared rule corpus:

- **Create** — recommend and build the right chart from a question and/or a dataset, via an
  iterative loop: envision the ideal outcome, test it against the real data, build the
  chart for real, force the "so what", then polish delivery.
- **Review** — critique an existing chart (image, code, or spec) through three independent
  lenses — integrity, form, and delivery — and return prioritized, concrete fixes.

The procedure for both lives in [SKILL.md](SKILL.md). Everything else is a rule corpus the
agent loads one file at a time, as each decision comes up.

Throughout, the agent is meant to work as a companion: it asks a clarifying question only
when the answer would change the chart, and reports the core choices as it makes them —
the target form, what the data turned out to support, and the takeaway that survived —
without narrating every rule it applies.

## Install

Claude Code, Cursor, and Codex all read the Agent Skill format natively — a `SKILL.md`
plus reference files loaded on demand — so no tool-specific copy of this content exists or
is needed. They differ only in *where* they look, and no single directory serves all three.
Installing is therefore just cloning to the right path.

**Claude Code** — install as a plugin, which handles updates and versioning:

```sh
/plugin marketplace add neil-oliver/data-storytelling-skills
/plugin install data-viz-playbook@data-storytelling-skills
```

Or clone straight into a skills directory — `~/.claude/skills/<name>/` for all projects,
`.claude/skills/<name>/` for one:

```sh
git clone https://github.com/neil-oliver/data-storytelling-skills ~/.claude/skills/data-viz-playbook
```

**Cursor and Codex** — both read `~/.agents/skills/` (and `.agents/skills/` inside a
project), so one clone covers them:

```sh
git clone https://github.com/neil-oliver/data-storytelling-skills ~/.agents/skills/data-viz-playbook
```

**All three from one copy** — skill directories may be symlinked, so clone once and link it
into each root:

```sh
git clone https://github.com/neil-oliver/data-storytelling-skills ~/skills/data-viz-playbook
ln -s ~/skills/data-viz-playbook ~/.claude/skills/data-viz-playbook   # Claude Code
ln -s ~/skills/data-viz-playbook ~/.agents/skills/data-viz-playbook   # Cursor + Codex
```

Which roots each tool reads:

| Directory | Claude Code | Cursor | Codex |
| --- | :---: | :---: | :---: |
| `.claude/skills/` | yes | yes, via a compatibility root users can switch off | no |
| `.agents/skills/` | no | yes | yes |
| `.codex/skills/` | no | yes, via the same compatibility root | yes |
| `.cursor/skills/` | no | yes | no |

Once installed, each tool loads the skill on its own whenever a task involves charts, or on
request by name (`/data-viz-playbook` in Claude Code and Cursor).

**Other harnesses** — point the agent at `SKILL.md` and give it file access to the repo;
the skill assumes nothing beyond the ability to read files and produce charts in whatever
medium the task uses.

**Obsidian** — the repo doubles as a vault: open the folder in Obsidian and the standard
Markdown links resolve like wikilinks.

## Layout

```
SKILL.md                    the procedure: entry points, the create loop, the review pass,
                            and where parallel work pays off
data.md                     what to plot and how to shape it (slices, baselines,
                            statistics, normalization, binning, missing data)
so-what.md                  the gate: no one-sentence takeaway, no chart
anti-patterns.md            the ship checklist: honesty, distortion, and bias failures
elevation-swaps.md          default chart → sharper reframe, when the obvious form fails
audience-and-presentation.md  tailoring depth, framing, and sequencing to a reader or room
chart-types/                one file per chart family; 00-selection.md maps
                            analytical task → form and routes to the right file
delivery/                   one file per presentation topic (titles, axes, color, labels,
                            annotations, decluttering, dashboards, interaction, …);
                            00-principles.md holds the cross-cutting rules
```

`SKILL.md` names what each corpus file covers, so the agent picks the right one before
opening anything. Each corpus file then opens with `scope` and `use_when` frontmatter that
confirms in two lines whether it applies — useful to the agent that just opened it, and to
anyone maintaining the rules.
