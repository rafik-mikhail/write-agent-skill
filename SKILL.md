---
name: write-agent-skill
description: Design, draft, revise, or audit reusable AI agent skills and SKILL.md instruction packages. Use when creating or improving a skill's scope, trigger description, workflow, supporting references or scripts, safety boundaries, and evaluations; tailor the skill to the host agent and real tasks.
---

# Write agent skill

## Objective

Deliver a runnable-by-an-agent instruction package for one coherent, reusable job. Ground it in the user's task, examples, tool environment, existing artifacts, and corrections. If no real examples are available, label assumptions and draft minimal testable instructions rather than inventing product-specific APIs. Complete and present the actual requested skill, not only a plan, progress report, or critique.

## Define the contract

1. State the trigger: the task and input that should activate this skill, plus adjacent requests that should not. Write the `description` as a concise routing rule specifying what it does and when to use it.
2. State the required and optional inputs, the agent's allowed authority, the intended output, and the definition of done. Resolve overlap with neighboring skills at the handoff; do not merge distinct stages just because they share a topic.
3. Mark which behaviors are mandatory safety or correctness gates, which are default heuristics, and which are optional enhancements. Instructions cannot enforce runtime permissions: use platform controls for filesystem, network, and tool access.

## Draft `SKILL.md`

Use YAML frontmatter with a lowercase hyphenated `name` matching its folder and a specific `description`. Follow the host platform's format and capabilities; do not assume optional metadata or `allowed-tools` enforces access across platforms.

Keep the body lean: job and boundary, inputs, decision procedure, stop/failure handling, output contract, and non-obvious gotchas. Give a default path rather than a menu of equal alternatives. Give exact steps for fragile operations; leave room for justified judgment in context selection. Avoid restating the same prohibition in every section or embedding a one-off task's answer as a general procedure.

Move large domain references to focused `references/` files, and tell the agent exactly when to read them. Add reusable scripts for repetitive deterministic work only after confirming their runtime dependencies and validation behavior. Keep references directly reachable from `SKILL.md`, and do not claim that a draft has been installed, executed, or validated when it has not.

## Test and revise

Start with 2–3 representative cases, including an edge case; add negative-trigger and adversarial cases when the skill acts on untrusted content or has important boundaries. Run fresh sessions with and without the skill or against the previous draft. Grade observable outputs and tool behavior, not how polished the instructions sound. Inspect traces for unnecessary steps, missed evidence, false activations, and scope creep. For mechanical checks use code; have humans inspect substantive judgments. Remove instructions that add cost without preventing a real failure.

## Delivery check

Before responding, verify that the complete requested artifact is actually present and internally consistent. When the user asks for the full Markdown, deliver the entire current `SKILL.md`, not patch fragments. If creating a file, verify that it exists and contains the full draft; report untested status honestly. Briefly state what changed and any remaining validation needs. Do not turn a request for one skill into an unrelated suite without a clear request.
