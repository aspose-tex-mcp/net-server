# Connect an MCP client

The TeX/.NET endpoint is `/tex/net/mcp/v1/streamable-http`. For the local README launch command, use `http://127.0.0.1:8080/tex/net/mcp/v1/streamable-http`. Remote clients use the endpoint exposed by your deployment.

## GitHub Copilot in VS Code

Add this server to the workspace `.vscode/mcp.json`:

```json
{
  "servers": {
    "tex-net": {
      "type": "http",
      "url": "https://YOUR_MCP_HOST/tex/net/mcp/v1/streamable-http"
    }
  }
}
```

Replace the host placeholder and configure credentials using the client's supported mechanism and the engine's authentication settings. Keep secrets out of committed files.

Start `tex-net` through **MCP: List Servers**, enable its tools in Copilot Agent mode, and ask a TeX/.NET question. Inspect tool calls and citations after content has been ingested and published. Installing an MCP server does not create a custom agent in the agent picker.

A dedicated TeX Copilot agent repository is pending publication. No custom agent or compilation sandbox is included here.

## Other clients

Use the client's HTTP MCP transport and authentication configuration. Some clients use `mcpServers` instead of VS Code's `servers` object. Consult the pinned engine's `MCP-SERVER.md` for supported transports and tools.

A successful initialization confirms protocol connectivity; it does not establish that indexes contain TeX content. Verify real retrieval after publication.
