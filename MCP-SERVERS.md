# MCP (Model Context Protocol) Server Setup

This document provides comprehensive information about MCP servers and their setup across different AI coding tools.

## What is MCP?

Model Context Protocol (MCP) is an open standard that allows AI assistants to connect to external servers that provide additional tools, data sources, and capabilities. MCP servers extend AI functionality in specific domains while maintaining security and modularity.

### Key Benefits

- **Extensibility**: Add new capabilities without modifying the core AI system
- **Security**: Controlled access to external resources through standardized protocols
- **Modularity**: Use only the servers you need for your specific workflow
- **Interoperability**: Works across different AI tools that support MCP

## Recommended MCP Servers

### Desktop Commander

- **Purpose**: File system operations, process management, and system interactions
- **Package**: `@wonderwhy-er/desktop-commander`
- **Use Cases**: File manipulation, running system commands, process monitoring

### Filesystem

- **Purpose**: Secure file system access to specified directories
- **Package**: `@modelcontextprotocol/server-filesystem`
- **Use Cases**: Reading/writing files, directory operations, file searches
- **Security**: Only grants access to explicitly specified directories

### Memory

- **Purpose**: Persistent memory and knowledge graph capabilities
- **Package**: `@modelcontextprotocol/server-memory`
- **Use Cases**: Storing context across sessions, building knowledge graphs

### Sequential Thinking

- **Purpose**: Detailed problem-solving through structured thought processes
- **Package**: `@modelcontextprotocol/server-sequential-thinking`
- **Use Cases**: Complex reasoning, step-by-step analysis, debugging

### Context7

- **Purpose**: Access to up-to-date documentation for popular libraries and frameworks
- **Package**: `@upstash/context7-mcp`
- **Use Cases**: Getting current documentation, API references, best practices

### Brave Search

- **Purpose**: Web search capabilities through the Brave Search API
- **Package**: `@modelcontextprotocol/server-brave-search`
- **Use Cases**: Real-time information retrieval, research, current events
- **Requirements**: Brave Search API key

### Kubernetes

- **Purpose**: Kubernetes cluster management and operations
- **Package**: `mcp-server-kubernetes`
- **Use Cases**: Cluster management, deployment operations, monitoring

## Tool-Specific Installation

### Claude Code CLI

Claude Code provides built-in MCP support with simple installation commands.

#### Prerequisites

- Node.js installed on your system
- Claude Code CLI installed and configured

#### Installation Commands

**Desktop Commander**:

```bash
claude mcp add-json desktop-commander '{
  "command": "npx",
  "args": ["-y", "@wonderwhy-er/desktop-commander"]
}' -s user
```

**Filesystem** (adjust paths as needed):

```bash
claude mcp add-json filesystem '{
  "command": "npx",
  "args": [
    "-y",
    "@modelcontextprotocol/server-filesystem",
    "/Users/your-username/git",
    "/Users/your-username/Downloads"
  ]
}' -s user
```

**Memory**:

```bash
claude mcp add-json memory '{
  "command": "npx",
  "args": [
    "-y",
    "@modelcontextprotocol/server-memory"
  ]
}' -s user
```

**Sequential Thinking**:

```bash
claude mcp add-json sequential-thinking '{
  "command": "npx",
  "args": [
    "-y",
    "@modelcontextprotocol/server-sequential-thinking"
  ],
  "env": {}
}' -s user
```

**Context7**:

```bash
claude mcp add-json context7 '{
  "command": "npx",
  "args": ["-y", "@upstash/context7-mcp@latest"]
}' -s user
```

**Brave Search** (replace with your API key):

```bash
claude mcp add-json brave-search '{
  "command": "npx",
  "args": [
    "-y",
    "@modelcontextprotocol/server-brave-search"
  ],
  "env": {
    "BRAVE_API_KEY": "your-brave-api-key-here"
  }
}' -s user
```

**Kubernetes**:

```bash
claude mcp add-json kubernetes '{
  "command": "npx",
  "args": ["mcp-server-kubernetes"]
}' -s user
```

#### Managing Servers

**Check server status**:

```bash
claude mcp status
```

**List all servers**:

```bash
claude mcp list
```

**Remove a server**:

```bash
claude mcp remove server-name
```

**View server logs**:

```bash
claude mcp logs server-name
```

#### Post-Installation

1. Verify installation with `claude mcp status`
2. Restart your Claude Code session to activate new servers
3. Test functionality by asking Claude to use the new capabilities

### Other AI Tools

MCP support varies across different AI tools. Check your specific tool's documentation for MCP integration capabilities.

#### General MCP Integration Patterns

- **Configuration Files**: Many tools support MCP through JSON/YAML configuration
- **Environment Variables**: Server configurations often use environment variables for API keys
- **Plugin Systems**: Some tools integrate MCP through their plugin architecture

## Security Considerations

### File System Access

- **Filesystem Server**: Only specify directories you trust the AI to access
- **Path Validation**: Ensure paths don't include sensitive system directories
- **Regular Audits**: Periodically review which directories are accessible

### API Keys and Credentials

- **Secure Storage**: Never commit API keys to version control
- **Environment Variables**: Use environment files (.env) that are gitignored
- **Key Rotation**: Regularly rotate API keys and access tokens
- **Minimal Permissions**: Use API keys with the minimum required permissions

### System Access

- **Desktop Commander**: Provides broad system access - use carefully in shared environments
- **Process Management**: Be cautious with process manipulation capabilities
- **Network Access**: Monitor which servers have network connectivity

## Troubleshooting

### Common Issues

**Server not connecting**:

1. Verify Node.js is installed and accessible
2. Check that the server package exists and is current
3. Restart your AI tool after adding servers
4. Review server logs for specific error messages

**Permission errors**:

- Ensure your AI tool has necessary system permissions
- On macOS, grant Terminal or your AI tool access to required directories
- Check file/directory permissions for specified paths

**API key issues**:

- Verify API keys are valid and active
- Check environment variable syntax in server configuration
- Ensure API keys have sufficient permissions for intended operations

**Performance issues**:

- Monitor system resources when running multiple servers
- Consider disabling unused servers to reduce resource consumption
- Check for conflicting server configurations

### Getting Help

- Check the official MCP documentation at [modelcontextprotocol.io](https://modelcontextprotocol.io)
- Review individual server documentation on GitHub/npm
- Join community forums for your specific AI tool
