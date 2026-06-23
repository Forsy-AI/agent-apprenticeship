# Agent Apprenticeship

[![npm version](https://img.shields.io/npm/v/agent-apprenticeship.svg)](https://www.npmjs.com/package/agent-apprenticeship)

The living ecosystem where AI agents learn from real-world work through iterative workflow loops, reusable experience, and collective training signal exchange.

```bash
npx agent-apprenticeship init
```

![Agent Apprenticeship](agent-apprenticeship.png)

As agents move into long-horizon, economically valuable work, Agent Apprenticeship creates the open infrastructure where real-world tasks generate reusable learning signals and complex workflows advance through agent loops that turn execution into shared improvement.

Agent Apprenticeship is designed for a compounding exchange of agent work experience: economically valuable task execution generates training signals, those signals improve future work, and future work creates new reusable experience for the ecosystem.

Agent Apprenticeship is built for iterative workflow loops across domains, from simple tasks to complex specialized work. Apprentice agents work with mentor agents or human experts to complete long-horizon, real-world tasks, while each workflow generates reusable learning signals for the ecosystem.

The first seed dataset includes:

* 500+ curated seed tasks sourced and grounded from real world
* 495 reusable agent lessons
* 1000+ full agent execution traces
* 1000+ agent work episodes / task rollouts

The seed dataset spans specialized economically valuable tasks across domains and forms the first layer of the Agent Apprenticeship ecosystem.

Agent Apprenticeship is now available for anyone to start using with local agents including Codex, Cursor, Claude Code, OpenClaw, OpenCode, Hermes Agent, and custom agents, alongside different model providers. Users can run automated agent workflow loops locally, contribute agent learning signals back to the ecosystem, and use shared ecosystem signals to improve their own agents.

Agent Apprenticeship is about the future of work and the economic value of agents. For every task executed through Agent Apprenticeship, the system can estimate task-level economic value, especially across specialized domains. It is built for everyday use to improve agent performance and outcome quality, while enabling users to exchange agent work experience with each other and with domain-expert-led agents in one living ecosystem.

## Install

```bash
npx agent-apprenticeship init
```

Or install globally:
```bash
npm install -g agent-apprenticeship
apprentice init
```

The installed command is:

```bash
apprentice
```

The long-form command also remains available:

```bash
agent-apprenticeship
```

## Quickstart

Start Agent Apprenticeship:

```bash
npx agent-apprenticeship init
```

The setup flow detects installed Apprentice Agents such as Codex, Cursor, Claude Code, OpenClaw, OpenCode, Hermes Agent, and Custom agents.

Check your setup:

```bash
apprentice settings
apprentice doctor
```

Configure your Apprentice Agent, Mentor Model Provider, and Mentor Mode:

```bash
apprentice configure
apprentice configure model
apprentice settings
```

Mentor Modes:

- `model-assisted` — automated
- `expert-led` — manual
- `hybrid` — automated + manual

Store Mentor Model Provider keys in:

```bash
~/.agent-apprenticeship/.env.local
```

Example:

```bash
OPENAI_API_KEY=""
ANTHROPIC_API_KEY=""
GEMINI_API_KEY=""
OPENROUTER_API_KEY=""
```

You can also use shell environment variables for the current terminal session:

```bash
export OPENAI_API_KEY="..."
apprentice doctor
```

Run your first task:

```bash
apprentice run "Create a short market map for AI procurement tools."
```

When the run completes, Agent Apprenticeship prints the local run folder, artifacts path, and agent experience package path.

Inspect the generated package:

```bash
apprentice bundle inspect <package_path>
apprentice bundle check <package_path>
```

Configure maximum loop depth for iterative runs:

```bash
apprentice settings
```

For a one-off terminal session, you can also set:

```bash
export AA_MAX_ITERATIONS=3
```

Configure ecosystem sharing:

```bash
apprentice ecosystem configure --repo Forsy-AI/agent-apprenticeship
apprentice ecosystem configure --auto-share manual
```

Auto-share modes:

- `manual` — no automatic sharing
- `ask` — ask before sharing
- `automatic` — share automatically when configured

Share the generated agent experience package with the public ecosystem:

```bash
apprentice ecosystem contribute <package_path>
```

Explore ecosystem experience:

```bash
apprentice ecosystem list
apprentice ecosystem search cloud
apprentice ecosystem inspect aa-seed-task-501
apprentice ecosystem pull aa-seed-task-501
```

Turn ecosystem experience into an Experience Pack:

```bash
apprentice learn create aa-seed-task-501
apprentice learn preview <pack_id>
apprentice learn keep <pack_id>
```

Use an Experience Pack in a new run:

```bash
apprentice run "Create a release checklist for an AI agent project." --experience-pack <pack_id>
```

## Apprentice Agents

Available Apprentice Agents:

* Codex
* Cursor
* Claude Code
* OpenClaw
* OpenCode
* Hermes Agent
* Custom

Agent Apprenticeship auto-detects installed CLIs. If multiple are detected, choose one during setup.

Custom lets you provide a command template:

```bash
apprentice configure agent custom --command-template "my-agent run --workspace {workspace} --prompt-file {prompt_file}"
```

## Mentor Model Providers

Store local keys in:

```text
~/.agent-apprenticeship/.env.local
```

Example:

```bash
OPENAI_API_KEY=""
ANTHROPIC_API_KEY=""
GEMINI_API_KEY=""
OPENROUTER_API_KEY=""
```

Configure:

```bash
apprentice configure model
apprentice doctor
```

## Mentor Modes

```bash
apprentice run "..." --mentor-mode model-assisted
apprentice run "..." --mentor-mode expert-led
apprentice run "..." --mentor-mode hybrid
```

* `model-assisted`: Mentor Model Provider handles the mentor loop.
* `expert-led`: human expert checkpoints guide the mentor loop.
* `hybrid`: Mentor Model Provider drafts and human expert checkpoints approve or edit.

## Ecosystem Search

The public ecosystem brings together the seed dataset and community-contributed agent experience packages in one searchable network.

Explore ecosystem experience:

```bash
apprentice ecosystem list
apprentice ecosystem search cloud
apprentice ecosystem inspect aa-seed-task-501
apprentice ecosystem pull aa-seed-task-501
```

The seed dataset is included under:

```text
seed_dataset/
```

## Ecosystem Learning

Pulled ecosystem experience can be used directly or turned into Experience Packs:

```bash
apprentice learn create aa-seed-task-501
apprentice learn preview <pack_id>
apprentice learn replay <pack_id>
apprentice learn keep <pack_id>
apprentice run "Create a related incident response checklist." --experience-pack <pack_id>
apprentice learn revert <pack_id>
```

Use active packs explicitly:

```bash
apprentice run "..." --use-active-experience-packs
apprentice run "..." --no-experience-packs
```

## Contribution Bundles

Runs produce Contribution Bundles.

Contribute one to the public ecosystem:

```bash
apprentice ecosystem contribute <bundle_path>
apprentice bundle contribute <bundle_path>
```

Public ecosystem:

https://github.com/Forsy-AI/agent-apprenticeship

## Ecosystem Auto-Share

Default mode is Manual.

```bash
apprentice ecosystem configure --repo Forsy-AI/agent-apprenticeship
apprentice ecosystem configure --auto-share manual
apprentice ecosystem configure --auto-share ask
apprentice ecosystem configure --auto-share automatic
apprentice ecosystem status
```

Requirements:

* GitHub CLI installed
* `gh` authenticated
* ecosystem repo configured

## Search, Inspect, Pull

Discover and export ecosystem experience:

```bash
apprentice ecosystem search <query>
apprentice ecosystem inspect <id>
apprentice ecosystem pull <id>
```

## Public Repo Structure

```text
seed_dataset/
ecosystem/
ecosystem/contributions/
schemas/
examples/
```

## Development Commands

```bash
.venv/bin/python -m pytest -q tests
PYTHONPATH=src .venv/bin/python -m compileall -q src tests scripts examples
bash scripts/export_public_repo.sh
```
