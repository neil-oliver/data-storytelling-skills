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

## Install

**Claude Code** — clone into your skills directory (the directory name becomes the skill
name):

```sh
# personal (all projects)
git clone https://github.com/neil-oliver/data-storytelling-skills ~/.claude/skills/data-viz-playbook

# or per-project
git clone https://github.com/neil-oliver/data-storytelling-skills .claude/skills/data-viz-playbook
```

Claude then applies the skill automatically whenever a task involves charts, or on demand
via `/data-viz-playbook`.

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

Every corpus file carries `scope` and `use_when` frontmatter so an agent can decide
whether to load it without opening it.
