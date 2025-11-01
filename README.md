# mcp-server-tavily

Zed extension that wraps the [`tavily-mcp`](https://www.npmjs.com/package/tavily-mcp) MCP server.

## Configuration

This MCP server requires an API key.

1. Sign up for a [Tavily API account](https://tavily.com)
2. Choose a plan (Free tier available with 1,000 queries/month)
3. Generate your API key [from the dashboard](https://app.tavily.com/home)

In your Zed settings:

**Option 1: Install via Zed Extensions (Recommended)**
```json
{
    "context_servers": {
        "mcp-server-tavily": {
          "settings": {
              "tavily_api_key": "YOUR_API_KEY"
          }
        }
    }
}
```

**Option 2: Custom MCP Server Configuration**
If you prefer to add it as a custom server instead of installing the extension:

```json
{
    "context_servers": {
        "tavily": {
            "command": "node",
            "args": ["node_modules/tavily-mcp/build/index.js"],
            "env": {
                "TAVILY_API_KEY": "YOUR_API_KEY"
            }
        }
    }
}
```

**Note for Custom Server Setup:**
- You must first install tavily-mcp locally: `npm install tavily-mcp`
- Replace `YOUR_API_KEY` with your actual Tavily API key
- Adjust the path to match your project structure if needed

## Installation

To install this extension in Zed:

1. Open Zed
2. Open the command palette (`Ctrl+Shift+P` or `Cmd+Shift+P`)
3. Type "Extensions: Install Extensions" and press Enter
4. Search for "mcp-server-tavily" and install it

Once installed, configure your API key in Zed settings as shown above.

## Features

- Web search functionality using Tavily's powerful search API
- Integration with Zed's Model Context Protocol
- Automatic package management and updates
- Enterprise-grade error handling and logging

## Requirements

- Zed editor
- Node.js (for the tavily-mcp package)
- Tavily API key

## Version History

- **0.0.3**: Updated zed_extension_api to 0.7.0 and tavily-mcp to 0.2.10
- **0.0.2**: Initial release with basic functionality

## License

MIT License - see LICENSE file for details

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.