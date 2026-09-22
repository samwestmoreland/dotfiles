# opencode config

`opencode.json` is my [opencode](https://opencode.ai) configuration.

## Setup

Symlink (or copy) it into place:

```sh
ln -s "$PWD/opencode.json" ~/.config/opencode/opencode.json
```

## Required environment variables

Secrets and internal hostnames are pulled out of the committed file via
`{env:...}` interpolation. Set these in your shell rc (not committed):

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
