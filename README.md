# Awesome Claude Fable 5.2 [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/) [![Link check](https://github.com/git-sanbu/awesome-claude-fable-5-2/actions/workflows/links.yml/badge.svg)](https://github.com/git-sanbu/awesome-claude-fable-5-2/actions/workflows/links.yml)

A curated, source-linked guide to **Claude Fable 5.2** — Anthropic's frontier model announced on November 9, 2026 together with its gated sibling **Claude Mythos 5.2** — covering official documentation, practical prompting patterns, GitHub projects, and community demos shared on X. Maintained independently; not affiliated with Anthropic.

[简体中文](README.zh-CN.md) · [Official resources](docs/official-resources.md) · [Resource directory](docs/README.md) · [Best practices](docs/best-practices.md) · [GitHub projects](docs/projects.md) · [X showcases](docs/x-showcases.md) · [Contribute](CONTRIBUTING.md)

**Last researched: 2026-11-11.** Community claims and demos have not been independently reproduced; stars are snapshots, not proof of trending growth. Availability, model names and pricing can change: consult [official resources](docs/official-resources.md) for current details.

## Frequently asked questions

### What is Claude Fable 5.2?

Claude Fable 5.2 is a large language model Anthropic [announced on November 9, 2026](https://www.anthropic.com/claude-fable-and-mythos-5-2), positioned for the most ambitious open-ended technical work. Per the [platform documentation](https://platform.claude.com/docs/en/models/fable-5-2/whats-new-fable-5-2) it has a 1M-token context window, 128k max output tokens, and adaptive thinking that is always on and controlled through an `effort` parameter.

### What is it used for?

Anthropic positions Fable/Mythos for frontier agentic and research work, and demonstrates it on long-running coding, formalization, simulation and creative-coding tasks; for most everyday coding and knowledge tasks Anthropic recommends starting with Claude Opus 5.5. Community projects in this list apply Fable 5.2 to browser games, 3D scenes, Blender animation, HTML visual design and operating-system prototypes — see [use cases](#use-cases) below.

### How is Fable 5.2 related to Mythos 5.2?

They are the [same underlying model](https://www.anthropic.com/claude-fable-and-mythos-5-2): Fable 5.2 adds cybersecurity and biology safeguards and is available to all users, while Mythos 5.2 is restricted to organizations vetted through Anthropic's Cyber Verification Program or Life Sciences Verification Program.

### How do I get access?

Fable 5.2 is available to all Claude API customers as `claude-fable-5-2`, plus Amazon Bedrock, Google Cloud, and Microsoft Foundry; Mythos 5.2 (`claude-mythos-5-2`) requires verification-program membership. Model IDs, pricing ($8/$40 per million tokens at launch, with an optional 2.5x fast mode) and retention rules are summarized with sources on the [official resources](docs/official-resources.md) page.

### Where do I learn to prompt it?

Start with Anthropic's [Fable 5.2 prompting guide](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2), then see our summary of [what Anthropic recommends](docs/best-practices.md#what-anthropic-recommends-for-fable-52) — effort calibration, early stopping, code ownership, subagent delegation and more — with reusable [prompt templates](docs/best-practices.md#coding-task-template).

## Start here

1. [Anthropic announcement: Claude Fable 5.2 and Mythos 5.2](https://www.anthropic.com/claude-fable-and-mythos-5-2) - Official launch, evaluations, safeguards and availability.
2. [Prompting Claude Fable 5.2](https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-fable-5-2) - Official prompting guidance.
3. [Official resources](docs/official-resources.md) — launch, docs, what's-new and pricing pages with sourced model facts.
4. [Our best practices and reusable prompts](docs/best-practices.md) — scope work, define acceptance checks, and verify outputs.
5. [Browse projects](docs/projects.md) or [community showcases](docs/x-showcases.md) for real examples and source links.

## Use cases

What people are building with Fable 5.2, and where to look in this list:

| I want to build…                        | Look at                                                                                                                                                                                                                                                           |
| --------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Browser games and interactive toys      | [saltline-fable-5.2](https://github.com/realcodebear/saltline-fable-5.2) · [fable52-fps-repro](https://github.com/wquguru/fable52-fps-repro) · [xray-mirror](https://github.com/MasterOfVFX2070/xray-mirror) · [game mashups in X showcases](docs/x-showcases.md) |
| 3D scenes, globes and simulations       | [earth-whole-story](https://github.com/arpitpatel25/earth-whole-story) · [Spectra](https://github.com/Seawolf0/Spectra) · [blender-fable-5.2](https://github.com/realcodebear/blender-fable-5.2)                                                                  |
| Video, motion design and animation      | [fable-vfx](https://github.com/bhavya-gx/fable-vfx) · [blackout](https://github.com/anstapnever/blackout) · [X showreels and anime shorts](docs/x-showcases.md)                                                                                                   |
| Visual HTML pages and design studies    | [Claude Fable 5.2 HTML Files](https://github.com/MiaAI-Lab/Claude-Fable-5.2-HTML-Files)                                                                                                                                                                           |
| Systems and OS prototypes               | [sumi-os-claude-fable-5-2](https://github.com/hama-jp/sumi-os-claude-fable-5-2)                                                                                                                                                                                   |
| Prompting tools and Claude Code plugins | [nativeprompt](https://github.com/edvardgrishin27/nativeprompt) · [oh-my-fable](https://github.com/Junhan2/oh-my-fable) · [prompt-studio](https://github.com/bwoliveira/prompt-studio)                                                                            |
| Curated collections to browse           | [awesome-claude-fable-5-2-use-cases](https://github.com/EvoLinkAI/awesome-claude-fable-5-2-use-cases) · [awesome-fable-5.2](https://github.com/fengyiqicoder/awesome-fable-5.2) · [awesome-fable5-2-videos](https://github.com/yihui-dev/awesome-fable5-2-videos) |

## Featured GitHub projects

| Project                                                                                        | Why explore it                                                        | Evidence                           |
| ---------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- | ---------------------------------- |
| [nativeprompt](https://github.com/edvardgrishin27/nativeprompt)                                | Offline prompt and instruction-file review against vendor guidance.   | Project description; 128 stars     |
| [Awesome Fable 5.2 Use Cases](https://github.com/EvoLinkAI/awesome-claude-fable-5-2-use-cases) | Large collection of linked use cases and evaluations.                 | Curated secondary source; 78 stars |
| [Claude Fable 5.2 HTML Files](https://github.com/MiaAI-Lab/Claude-Fable-5.2-HTML-Files)        | Visual HTML studies with prompts and screenshots.                     | Project description; 68 stars      |
| [oh-my-fable](https://github.com/Junhan2/oh-my-fable)                                          | Claude Code plugin translating prompting guidance into working rules. | Project README; 61 stars           |
| [saltline-fable-5.2](https://github.com/realcodebear/saltline-fable-5.2)                       | Single-HTML-file browser FPS described as generated from one prompt.  | Unofficial mirror; 46 stars        |
| [xray-mirror](https://github.com/MasterOfVFX2070/xray-mirror)                                  | Webcam-based interactive X-ray mirror experiment.                     | Creator's description; 36 stars    |

Stars were retrieved from the GitHub API on 2026-11-11 and can change. See [all 21 selected projects](docs/projects.md) for more context and selection criteria.

## Featured community examples

- [@kaif9998's launch showreel](https://x.com/kaif9998/status/2119903824848761287) - a short motion-design workflow as described by the creator, with [separate prompts](https://x.com/kaif9998/status/2119904086288118219) and a [secondary source](https://github.com/yihui-dev/awesome-fable5-2-videos/blob/main/prompts/kaif9998-761287.md).
- [@mattshumer_'s game mashup](https://x.com/mattshumer_/status/2119872098306810226) - a playable demo described as built from a single prompt; [source record](https://github.com/yihui-dev/awesome-fable5-2-videos/blob/main/prompts/mattshumer-810226.md).
- [@0kncn's Blender anime short](https://x.com/0kncn/status/2119901782482543073) - a 90-second animation experiment, with a detailed [shared prompt](https://x.com/0kncn/status/2119901786060259612) and [source record](https://github.com/yihui-dev/awesome-fable5-2-videos/blob/main/prompts/0kncn-543073.md).
- [@emollick's reverse Scooby-Doo game](https://x.com/emollick/status/2119876449494540554) - a parody game shared as a lighter launch-day example; [source record](https://github.com/yihui-dev/awesome-fable5-2-videos/blob/main/prompts/emollick-540554.md).
- [@maxleiter's Game of Life compiler](https://x.com/maxleiter/status/2119869170871652487) - a compiler that runs code inside Conway's Game of Life; [source record](https://github.com/yihui-dev/awesome-fable5-2-videos/blob/main/prompts/maxleiter-652487.md).

These entries were discovered through a third-party catalogue plus web search. The original X posts, engagement metrics and demos were not independently verified in this research; they are examples, not a verified ranking of viral posts. [More details](docs/x-showcases.md).

## How entries are selected

We favor original sources, a clear connection to Fable 5.2, practical learning value, and accessible artifacts or prompts. A repository author's claim is attributed to that author. Inclusion is not an endorsement, security review, benchmark, or guarantee of reproducibility. Report errors or suggest a resource via an issue or pull request.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to suggest a resource, correct a source, or report a broken link.

## License

Original text in this repository is available under [CC BY 4.0](LICENSE). Linked projects, prompts, media and trademarks remain subject to their respective owners' terms; no third-party content is relicensed here.
