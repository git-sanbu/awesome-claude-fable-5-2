# Claude Fable 5.2 best practices and prompt templates

[Home](../README.md) · [Resource directory](README.md) · [GitHub projects](projects.md) · [X showcases](x-showcases.md)

These are practical editorial recommendations for working with Claude and coding agents, not claims of measured Fable-specific performance. Start with [Anthropic's Fable 5.2 prompting guide](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2) and [official launch](https://www.anthropic.com/claude-fable-and-mythos-5-2). Consult current documentation for supported API parameters and model IDs.

## A repeatable workflow

1. **Define the outcome:** describe the user, concrete goal and deliverable.
2. **Supply context:** give the repository, relevant files, examples, inputs and constraints. Ask the agent to inspect existing conventions first.
3. **Set boundaries:** name files or systems in scope and operations needing human approval. Preserve unrelated changes.
4. **Specify acceptance checks:** name commands, interactions, edge cases and evidence you expect. Allow the agent to report a check it could not perform.
5. **Review and iterate:** inspect the actual output and diff, run checks independently where practical, and distinguish tested results from claims.
6. **Record the run:** save model/version, date, prompt, environment, inputs, costs when available, and all manual edits for reproducibility.

## Coding task template

```text
Goal: [observable result and user]
Context: [project, relevant paths, current behavior, evidence]
Scope and constraints: [allowed changes, compatibility, limits]
Acceptance: [tests, interactions, edge cases and expected behavior]
Inspect the project first, implement the change, run the appropriate checks,
and report changed files, results, assumptions and anything unverified.
```

## Research template

```text
Investigate [question] for [audience]. Prefer primary sources and link each
important claim. Separate evidence from inference, include dates and competing
explanations, and state what could not be verified. Deliver [format].
```

## Creative coding template

```text
Create [interactive experience] for [audience]. Art direction: [references,
palette, motion]. Required interactions: [list]. Constraints: [stack, devices,
performance, accessibility]. Verify [specific interactions] on [viewports],
then report what works and any remaining limitations.
```

## Comparisons and safety

Keep task, inputs, tool access, time and evaluation criteria consistent across models. Record retries and human interventions; do not infer general capability from one impressive clip. Review third-party code and permissions before running it, and avoid putting credentials or sensitive data into public examples.
