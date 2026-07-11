<div align="center">

# Sol ChatGPT OnSteruids 5.6

### A production-grade system prompt for GPT-5.6 Sol, Codex, and serious full-stack work

**One prompt. End-to-end engineering. High-end design. Bounded agents. Lower token waste.**

[![GPT-5.6 Sol](https://img.shields.io/badge/GPT--5.6-Sol-111111?style=flat)](SYSTEM_PROMPT.md)
[![Codex Ready](https://img.shields.io/badge/Codex-AGENTS.md-111111?style=flat)](AGENTS.md)
[![Prompt Only](https://img.shields.io/badge/Dependencies-None-111111?style=flat)](SYSTEM_PROMPT.md)
[![License](https://img.shields.io/badge/License-MIT-111111?style=flat)](LICENSE)

[**Open the system prompt**](SYSTEM_PROMPT.md) · [**Use with Codex**](AGENTS.md) · [**View raw**](https://raw.githubusercontent.com/shalevamin/Sol-ChatGpt-OnSteruids5.6/main/SYSTEM_PROMPT.md)

</div>

> [!IMPORTANT]
> This is a community-authored instruction layer. It does not replace or expose OpenAI's internal system prompt, and it is not affiliated with or endorsed by OpenAI.

## Recently Updated

| What | Date | Link |
|---|---|---|
| **Sol ChatGPT OnSteruids 5.6 system prompt** | July 11, 2026 | [Prompt](SYSTEM_PROMPT.md) |
| **Codex-ready version** | July 11, 2026 | [`AGENTS.md`](AGENTS.md) |

## What Is This?

Sol ChatGPT OnSteruids 5.6 is a single reusable prompt that turns GPT-5.6 Sol or Codex into a rigorous end-to-end software engineering agent.

It is designed to:

- work across frontend, backend, APIs, databases, infrastructure, security, testing, and product UX,
- inspect the repository before making assumptions,
- implement requested work instead of stopping at suggestions,
- preserve existing user changes and avoid destructive Git behavior,
- produce domain-appropriate, high-end interfaces instead of generic AI-looking UI,
- use subagents only when parallel work is genuinely useful,
- reduce token waste through targeted retrieval, compact context, and concise outputs,
- verify the result with tests, builds, runtime checks, and rendered UI inspection when relevant.

## Install

### Codex

Run this from the root of a project that does not already have an `AGENTS.md` file:

```bash
curl -fsSL https://raw.githubusercontent.com/shalevamin/Sol-ChatGpt-OnSteruids5.6/main/AGENTS.md -o AGENTS.md
```

Or clone the repository and copy the file manually:

```bash
git clone https://github.com/shalevamin/Sol-ChatGpt-OnSteruids5.6.git
cp Sol-ChatGpt-OnSteruids5.6/AGENTS.md /path/to/your-project/AGENTS.md
```

> [!WARNING]
> Do not overwrite an existing project `AGENTS.md` blindly. Merge the instructions when the repository already has project-specific rules.

### ChatGPT Projects

1. Open [`SYSTEM_PROMPT.md`](SYSTEM_PROMPT.md).
2. Copy the full contents.
3. Paste them into the project's instruction field.
4. Put task-specific requirements in the user message, not inside the reusable prompt.

### OpenAI API

```js
import fs from "node:fs";
import OpenAI from "openai";

const client = new OpenAI();
const instructions = fs.readFileSync("./SYSTEM_PROMPT.md", "utf8");

const response = await client.responses.create({
  model: "gpt-5.6-sol",
  instructions,
  input: "Implement the requested feature and verify it end to end.",
});

console.log(response.output_text);
```

## Core Behavior

### Engineering

The prompt requires the agent to trace the real runtime path, follow the repository's existing architecture, keep changes scoped, handle failures deliberately, protect compatibility, and finish with evidence.

### Design

The prompt treats design as product engineering. It requires a clear visual direction, real content, coherent typography and spacing, responsive behavior, accessibility, reduced-motion support, and rendered verification. It explicitly rejects generic purple gradients, card soup, glowing decoration, fake charts, and interchangeable AI-generated layouts.

### Agents

The root agent keeps ownership of requirements, architecture, writes, integration, and the final answer. Delegation is limited to concrete, independent work where the quality or speed gain exceeds the token and coordination cost. Agent depth is kept shallow by default.

### Token Economy

The prompt favors targeted file ranges, batched reads, compact evidence summaries, stable reusable instructions, on-demand specialist context, and short final reports. It spends more context only when ambiguity, risk, or failed verification justifies it.

## Files

| File | Use |
|---|---|
| [`SYSTEM_PROMPT.md`](SYSTEM_PROMPT.md) | ChatGPT Projects, API instructions, or another compatible developer/system instruction field |
| [`AGENTS.md`](AGENTS.md) | Drop-in project instructions for Codex |
| [`LICENSE`](LICENSE) | MIT license |

## Why One Prompt?

This repository deliberately avoids an oversized framework, installer, marketplace, agent catalog, or dozens of optional files. The product is the prompt. Open one file, add it to the instruction layer, and use it.

## Credits

The prompt was informed by public agent-system patterns, current coding-agent workflows, and the public [`system_prompts_leaks`](https://github.com/asgeirtj/system_prompts_leaks) archive. Its wording and composition are original.

## License

MIT. See [`LICENSE`](LICENSE).
