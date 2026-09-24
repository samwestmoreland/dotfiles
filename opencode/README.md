# OpenCode config

This directory contains the parts of my [OpenCode](https://opencode.ai)
configuration that should travel between machines: the base config, agents, skills,
and commands. Plugins, credentials, package installs, and UI state stay local.

## Setup

Run these commands from this directory:

```sh
mkdir -p ~/.config/opencode
ln -s "$PWD/opencode.json" ~/.config/opencode/opencode.json
ln -s "$PWD/agents" ~/.config/opencode/agents
ln -s "$PWD/skills" ~/.config/opencode/skills
ln -s "$PWD/command" ~/.config/opencode/command
```

If a destination already exists, merge or remove it before creating that symlink.
Leave the rest of `~/.config/opencode` as a real directory so OpenCode and its
plugins can keep their machine-local state there.

The config includes inline `explore` and `general` agents. The primary `smarty`
agent and specialist agents are file-backed under `agents/`.

## Required environment variables

The committed config uses `{env:...}` interpolation for secrets and internal
hostnames. Set these in your shell rc, rather than committing them:

| Variable            | Purpose                                          |
| ------------------- | ------------------------------------------------ |
| `LLM_API_KEY`       | API key for the OpenAI-compatible LLM provider   |
| `LLM_API_BASE_URL`  | Base URL for the LLM provider                     |
| `GLEAN_MCP_URL`     | Glean MCP endpoint URL                            |

Example:

```sh
export LLM_API_KEY="sk-..."
export LLM_API_BASE_URL="https://your-provider.example.com/"
export GLEAN_MCP_URL="https://your-glean-instance.example.com/mcp/default"
```
