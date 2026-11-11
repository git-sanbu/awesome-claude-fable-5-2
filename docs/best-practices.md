# Claude Fable 5.2 best practices and prompt templates

[Home](../README.md) · [Resource directory](README.md) · [GitHub projects](projects.md) · [X showcases](x-showcases.md) · [Official resources](official-resources.md)

These are practical editorial recommendations for working with Claude and coding agents, not claims of measured Fable-specific performance. Start with [Anthropic's Fable 5.2 prompting guide](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2) and [official launch](https://www.anthropic.com/claude-fable-and-mythos-5-2). Consult current documentation for supported API parameters and model IDs.

## What Anthropic recommends for Fable 5.2

The bullets below summarize Anthropic's own guidance for the model, from the [Fable 5.2 prompting guide](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2) and the [What's new in Claude Fable 5.2](https://platform.claude.com/docs/en/models/fable-5-2/whats-new-fable-5-2) page. Each bullet links to its source; performance figures quoted are vendor-reported from those pages, not independently verified.

- **[Calibrate effort (start at high)](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)** — Start at `high` effort (the Claude API default) and sweep `medium` and `xhigh` against your own evaluations rather than carrying over a setting tuned on Fable 5.1 or Opus 5.5. Anthropic reports most of the capability gain is already present at `high`, that gains above it are uneven and task-dependent, and that effort can be changed per message mid-workflow while preserving the prompt cache.
- **[Finish the whole task (fix early stopping)](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)** — On long multistep tasks the model can end its turn early (more often at `low`/`medium` effort), closing with a remaining-work list, an offer to continue, or a stop at an ordinary obstacle. The guide's system-prompt block tells the model to persist through ordinary obstacles while leaving deliberate blockers alone and reporting them; Anthropic reports it halved sessions ending with doable work left, at roughly +30% output tokens, so keep your own confirmation step for risky or irreversible actions.
- **[Approvals: answer specifically, name what the rules cover](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)** — When resuming a step the user approved, send a concrete instruction such as "Yes, run the migration on the staging database" rather than a bare acknowledgment, and make explicit what the approval covers.
- **[Say who owns the code](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)** — The model's behavior tracks what the prompt says about code ownership: with no ownership statement it tends to extend existing structure even when that duplicates code, while adding a sentence like "This codebase is yours" made it merge duplicated code in about half of Anthropic's test tries versus under a tenth without, at roughly 1.5x output tokens and more unrequested changes. Review the diff rather than the summary, leave the sentence out when minimal changes are wanted, and note that a scope-limiting rule elsewhere in the prompt does not cancel it.
- **[Keep users informed during long turns (progress-update thinking blocks)](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)** — Inter-tool-call updates now arrive as progress-update `thinking` blocks that are empty at the default `thinking.display: "omitted"`, so text-only clients look silent; set `display` to `"updates"` or `"summarized"` and render those blocks, and for still-quiet agents have the harness count silent tool-calling steps and append a turn-scoped system-message reminder after the latest tool results. Anthropic reports the reminder roughly halved the longest silent stretch; leave reminders in `messages`, since removing one invalidates later thinking blocks.
- **[Set expectations for subagents via the tool description](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)** — How much Fable 5.2 delegates depends on your harness prompts; when it over-delegates, rewrite the subagent-starting tool's description to state, in order, what a subagent costs, when delegation is and is not worth it, and how to brief a subagent. Anthropic reports the tested description cut delegation by about a third with the same task success; also check which model your harness runs subagents on, since they can dominate session cost.
- **[Keep caution from piling up (prune inherited rules and notes)](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)** — Fable 5.2 follows accumulated cautious instructions from memory, notes, instruction files and inter-agent messages very closely, and can over-ask for approvals as a result. The guide's remedy is to prune: delete stale notes and other inherited caution instead of letting it accumulate.
- **[Review instructions written for earlier models when migrating](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)** — Remove or retest on migration: standing delegation lines (which sit in system prompts, skills and agent files), harness-written token budgets in the prompt, and harness code that edits earlier turns, which breaks preserved thinking — use context editing, compaction or the documented thinking-block binding behavior instead, and otherwise keep history append-only. In Anthropic's testing, removing a large written budget lowered cost at equal performance.
- **[Make reports easy to follow (write for a low-context reader)](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)** — Readers of final reports and handoffs have not seen the tool calls or files behind them, so the guide supplies a system-prompt block asking for self-contained messages: key points first, plain words, no invented abbreviations, one idea per sentence and consistent terminology. Anthropic reports it made final reports less dense, with fewer semicolons and shorter sentences.
- **[Handle safeguard refusals (`stop_reason: "refusal"`)](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)** — Declined requests return HTTP 200 with `stop_reason: "refusal"` and a `stop_details.category` of `cyber`, `bio`, `frontier_llm`, `reasoning_extraction` or `general_harms`; benign cyber and life-sciences work can also trip the `cyber`/`bio` classifiers, and verification programs exist for legitimate blocked work. Do not instruct the model to write its reasoning in the response text (that triggers `reasoning_extraction`) — set `display: "summarized"` and read the thinking blocks instead, and retry refused requests on another model via fallback.
- **[Make instruction changes in new conversations only (prefix check)](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)** — On Fable 5.2 the API enforces the preserved-thinking prefix check on every account: changing `system`, `tools`, or an earlier message and then sending stored thinking blocks back can return a 400. Make instruction changes only in new conversations.
- **[Follow the migration order in "Where to start"](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2)** — Anthropic's prescribed migration sequence: set `effort` to `high` explicitly and run evals at `medium` and `xhigh`; audit carried-over system prompts, skills, agent files, memory and harness text; run your longest agentic tasks and note early stops, unnecessary approval asks, silence and over-delegation; then apply one guidance fix at a time, measuring effect and token cost on your own tasks.
- **[Use adaptive thinking via `effort`; no `budget_tokens` or forced tool use](https://platform.claude.com/docs/en/models/fable-5-2/whats-new-fable-5-2)** — Thinking is always on and adaptive is the only mode: `thinking {"type": "enabled"}` with `budget_tokens` and `{"type": "disabled"}` both return 400, so control depth with the `effort` parameter. Forced tool use (`tool_choice` of `"any"` or `"tool"`) also returns 400; use `auto` with strict tool use or JSON outputs for schema-valid output (structured outputs are unavailable under customer-managed encryption keys).
- **[Move computer use to the `computer_toolset_20260801` toolset](https://platform.claude.com/docs/en/models/fable-5-2/whats-new-fable-5-2)** — Fable 5.2 supports computer use only through the `computer_toolset_20260801` toolset; requests declaring the earlier `computer_20251124` tool return a 400 `invalid_request_error` on every platform except Amazon Bedrock, where the old tool still works as on Fable 5.1.
- **[Advisor tool: pair a Fable 5.2 executor with a Fable/Mythos 5.2 advisor](https://platform.claude.com/docs/en/models/fable-5-2/whats-new-fable-5-2)** — With the beta advisor tool the advisor must be at least as capable as the executor: a Fable 5.2 or Mythos 5.2 executor accepts only `claude-fable-5-2` or `claude-mythos-5-2` as advisor, and anything else (including 5.1 models) returns 400. Change the advisor `model` in the same change and only in new conversations (editing `tools` mid-conversation trips the prefix check), and note a Fable 5.2 advisor returns advice encrypted, which matters if your code reads the advice text.
- **[Expect model-specific behaviors when carrying prompts over](https://platform.claude.com/docs/en/models/fable-5-2/whats-new-fable-5-2)** — Some behaviors appear without code changes: "think less" lines do not stop thinking at `medium` and above, turns can end before work is done (worse at low/medium effort), code-ownership wording changes whether the model restructures or merely extends, long tool-call runs can pass with little user-facing text, delegation volume tracks harness prompts, and hard style limits can make prose choppy.
- **[Apply cross-model prompting best practices (clarity, examples, XML, long context)](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices)** — The general reference that applies to Fable 5.2 alongside the model-specific guide: be clear and direct, explain the why behind instructions, use diverse `<example>`-wrapped few-shots, structure mixed prompts with XML tags, put long documents above the query and ground answers in quotes from them. It also covers parallel tool-call steering, long-horizon state tracking, and the migration note to keep history append-only and pass thinking blocks back unchanged.

For launch details — model IDs, availability, pricing, fast mode and breaking API changes — see the collected [Official Claude Fable 5.2 resources](official-resources.md).

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
