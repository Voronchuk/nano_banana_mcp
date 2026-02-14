# Nano Banana Pro MCP Server 🍌

Local MCP server for image generation and editing using **Nano Banana Pro** (Gemini 3 Pro Image).

Forked from [ConechoAI/Nano-Banana-MCP](https://github.com/ConechoAI/Nano-Banana-MCP) with the model upgraded to `gemini-3-pro-image-preview`.

## Setup

### 1. Get a Gemini API key

Go to [Google AI Studio](https://aistudio.google.com/app/apikey) and create a key.
Make sure your account has access to the Gemini 3 Pro Image model.

### 2. Install locally

```bash
cd nano-banana-pro-mcp
npm install
npm run build
```

### 3. Configure your MCP client

**Claude Code** (`~/.claude.json` or project `.mcp.json`):

```json
{
  "mcpServers": {
    "nano-banana-pro": {
      "command": "node",
      "args": ["/absolute/path/to/nano-banana-pro-mcp/dist/index.js"],
      "env": {
        "GEMINI_API_KEY": "your-gemini-api-key"
      }
    }
  }
}
```

**Cursor** (MCP settings):

```json
{
  "nano-banana-pro": {
    "command": "node",
    "args": ["/absolute/path/to/nano-banana-pro-mcp/dist/index.js"],
    "env": {
      "GEMINI_API_KEY": "your-gemini-api-key"
    }
  }
}
```

**Claude Desktop** (`claude_desktop_config.json`):

```json
{
  "mcpServers": {
    "nano-banana-pro": {
      "command": "node",
      "args": ["/absolute/path/to/nano-banana-pro-mcp/dist/index.js"],
      "env": {
        "GEMINI_API_KEY": "your-gemini-api-key"
      }
    }
  }
}
```

Replace `/absolute/path/to/` with the actual path where you placed the project.

## Available Tools

| Tool | Description |
|------|-------------|
| `generate_image` | Create a new image from a text prompt |
| `edit_image` | Edit an existing image file with a prompt |
| `continue_editing` | Keep editing the last generated/edited image |
| `get_last_image_info` | Info about the last image (path, size) |
| `configure_gemini_token` | Set API key at runtime (prefer env var instead) |
| `get_configuration_status` | Check if the API key is configured |

## Generated images location

- **Linux/macOS**: `./generated_imgs/` in the working directory
- **Windows**: `%USERPROFILE%\Documents\nano-banana-images\`

## License

MIT (original license from ConechoAI/Nano-Banana-MCP)
