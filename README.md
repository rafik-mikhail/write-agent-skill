# Write Agent Skill

An agent skill for designing, writing, revising, or auditing reusable agent skills. It helps define when a skill should load, what it may do, what it must deliver, and how to evaluate it on representative tasks.

## Use the skill

Use [`SKILL.md`](SKILL.md) in your agent’s skill directory under `write-agent-skill/`. Give the agent the job you want to turn into a skill, the target agent or platform, and any representative tasks or existing drafts. The skill guides the agent toward a complete `SKILL.md`, with supporting files only when they serve a clear purpose.

## Use as agent instructions

Copy the [Write Agent Skill instruction gist](https://gist.github.com/rafik-mikhail/a4565c0bcc276ebb2793e854a5a4f162) into your agent’s instruction file. The gist contains the same guidance with `applyTo: "**"` front matter for tools that support it. If your agent accepts plain Markdown instructions, copy the body without the front matter.
