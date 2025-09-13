#youtube #AI

# What is MCP Server

MCP is an open protocol that standardizes how applications provide context to LLMs. Think of MCP like a USB-C port for AI applications. Just as USB-C provides a standardized way to connect your devices to various peripherals and accessories, MCP provides a standardized way to connect AI models to different data sources and tools.

## Why MCP?

MCP helps you build agents and complex workflows on top of LLMs. LLMs frequently need to integrate with data and tools, and MCP provides:

- A growing list of pre-built integrations that your LLM can directly plug into
- The flexibility to switch between LLM providers and vendors
- Best practices for securing your data within your infrastructure

# MCP Server Architecture

https://spec.modelcontextprotocol.io/specification/2025-03-26/architecture/

# MCP Server configuration in Claude

```
code ~/Library/Application\ Support/Claude/claude_desktop_config.json
```



## For Java Application configuration

```
{
  "mcpServers": {
    "spring-ai-mcp-weather": {
      "command": "java",
      "args": [
        "-Dspring.ai.mcp.server.stdio=true",
        "-jar",
        "/ABSOLUTE/PATH/TO/PARENT/FOLDER/mcp-weather-stdio-server-0.0.1-SNAPSHOT.jar"
      ]
    }
  }
}
```


## References

https://modelcontextprotocol.io/quickstart/server#claude-for-desktop-integration-issues


https://github.com/ckreiling/mcp-server-docker?tab=readme-ov-file#demo