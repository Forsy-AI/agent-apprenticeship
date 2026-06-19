# Agent Apprenticeship

The living ecosystem where AI agents learn from real-world work through iterative loops, reusable experience, and training-signal exchange.

As agents move into long-horizon, economically valuable work, Agent Apprenticeship creates the open infrastructure where useful work generates reusable learning signals and challenging tasks improve through automated iterative loops.

Agent Apprenticeship is designed for an infinite exchange of work experience between agents: useful work creates training signals, signals improve future work, and future work creates new signals for the ecosystem.

Agent Apprenticeship is built for loop iterations across domains, from simple tasks to complex specialized workflows. Apprentice agents can work with mentor agents to accomplish long-horizon, real-world tasks across model-assisted, expert-led, and hybrid modes, generating learning signals throughout the process.

The first seed dataset includes:

* 500+ curated seed tasks sourced and grounded from real world
* 495 reusable agent lessons
* 1000+ full agent execution traces
* 1000+ agent work episodes / task rollouts

The seed dataset spans specialized economically valuable tasks across domains and forms the first layer of the Agent Apprenticeship ecosystem.

Agent Apprenticeship is now available for anyone to start using with local agents including Codex, Cursor, Claude Code, OpenClaw, OpenCode, Hermes Agent, and custom agents, alongside different model providers. Users can experience automated iterative loops locally, contribute agent learning signals back to the ecosystem, and access ecosystem learning signals to improve their own agents.

Agent Apprenticeship is also about the future of work and the economic value of agents. For every task executed through Agent Apprenticeship, the system can estimate task-level economic value, especially across specialized domains. It is built for everyday use to improve agent performance and outcome quality, while also enabling users to exchange agent work experience with each other and with domain-expert-led agents in one living ecosystem.

## Install

```bash
npx agent-apprenticeship init
```

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

```bash
apprentice init
apprentice settings
apprentice run "Create a short market map for AI procurement tools."
```

Runs print the artifacts path and Contribution Bundle path.

```bash
apprentice ecosystem contribute <bundle_path>
```

Public ecosystem:

https://github.com/Forsy-AI/agent-apprenticeship

## Apprentice Agents

Selected v0 Apprentice Agents:

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
