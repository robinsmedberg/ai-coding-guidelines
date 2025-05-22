# AI Coding Guidelines

This repository contains a collection of guidelines and best practices for working with AI coding assistants. These guidelines are designed to help developers and teams effectively leverage AI tools in their development workflow.

## Table of Contents

- [Guidelines](#guidelines)
- [MCP Servers](#mcp-servers)
- [Using These Guidelines in Your Projects](#using-these-guidelines-in-your-projects)
  - [Windsurf](#windsurf)
  - [Claude Code CLI](#claude-code-cli)
  - [GitHub Copilot](#github-copilot)
  - [VS Code Extensions](#vs-code-extensions)
  - [JetBrains AI Assistant](#jetbrains-ai-assistant)
  - [Continue](#continue)
  - [Anthropic Claude API](#anthropic-claude-api)
  - [OpenAI Assistants API](#openai-assistants-api)
  - [General Integration Approaches](#general-integration-approaches)
- [Best Practices for Guideline Integration](#best-practices-for-guideline-integration)
- [Contributing](#contributing)

## Guidelines

- [Full Process for Coding with AI Coding Assistants](./Full%20Process%20for%20Coding%20with%20AI%20Coding%20Assistants.md) - A comprehensive guide to structuring your development process when working with AI assistants.

## MCP Servers

Model Context Protocol (MCP) allows AI assistants to connect to external servers that provide additional tools and capabilities. We provide comprehensive documentation for setting up MCP servers across different AI tools:

- [MCP Server Guide](./MCP-SERVERS.md) - Tool-agnostic guide covering MCP fundamentals, recommended servers  and tool-specific installation instructions with detailed security considerations and troubleshooting.

## Using These Guidelines in Your Projects

### Windsurf

To use these guidelines as default instructions in Windsurf, create a `.windsurf` file in your project root with the following content:

```json
{
  "defaultInstructions": "You are an AI assistant working on a coding project. Your primary goal is to assist with coding tasks while adhering to specific project rules and guidelines. Fetch and analyze https://github.com/agronod/ai-coding-guidelines/blob/main/Full%20Process%20for%20Coding%20with%20AI%20Coding%20Assistants.md before any other action and there after follow and enforce the rules."
}
```

### Claude Code CLI

To integrate these guidelines with Claude Code CLI:

1. Create or edit the `CLAUDE.md` file in your `~/.claude/` directory
2. Add the following content:

```markdown
You are an AI assistant working on a coding project. Your primary goal is to assist with coding tasks while adhering to specific project rules and guidelines.

<source_url><https://raw.githubusercontent.com/agronod/ai-coding-guidelines/refs/heads/main/Full%20Process%20for%20Coding%20with%20AI%20Coding%20Assistants.md></source_url>

Please refer to the full specification at the source URL above for complete details on project guidelines. They must be fetched and analyzed before any other action and there after followed and enforced.
```

For project-specific usage, you can create a `CLAUDE.md` file in your project root that references these guidelines along with project-specific instructions.

### GitHub Copilot

To integrate with GitHub Copilot:

1. In VS Code with Copilot Chat extension installed, use the command:

```
@github You are an AI assistant working on a coding project. Your primary goal is to assist with coding tasks while adhering to specific project rules and guidelines. Fetch and analyze https://github.com/agronod/ai-coding-guidelines/blob/main/Full%20Process%20for%20Coding%20with%20AI%20Coding%20Assistants.md before any other action and there after follow and enforce the rules.
```

2. For Copilot Chat in GitHub.com, use the `/guidance` command:

```
/guidance You are an AI assistant working on a coding project. Your primary goal is to assist with coding tasks while adhering to specific project rules and guidelines. Fetch and analyze https://github.com/agronod/ai-coding-guidelines/blob/main/Full%20Process%20for%20Coding%20with%20AI%20Coding%20Assistants.md before any other action and there after follow and enforce the rules.
```

Note: Due to context limitations, you may need to reference specific sections rather than the entire guidelines document.

### VS Code Extensions

For VS Code extensions that provide AI coding assistance:

#### Anthropic Claude Extension for VS Code

1. Open Settings (Ctrl+,)
2. Search for "Claude: Default System Prompt"
3. Add the following:

```
You are an AI assistant working on a coding project. Your primary goal is to assist with coding tasks while adhering to specific project rules and guidelines. Fetch and analyze https://github.com/agronod/ai-coding-guidelines/blob/main/Full%20Process%20for%20Coding%20with%20AI%20Coding%20Assistants.md before any other action and there after follow and enforce the rules.
```

#### OpenAI GPT Extension for VS Code

1. Open Settings (Ctrl+,)
2. Search for "OpenAI: System Instructions"
3. Add reference to the guidelines URL

### JetBrains AI Assistant

To integrate with JetBrains AI Assistant:

1. Go to Settings/Preferences
2. Navigate to Tools > AI Assistant > Custom Instructions
3. Add the following to your custom instructions:

```
You are an AI assistant working on a coding project. Your primary goal is to assist with coding tasks while adhering to specific project rules and guidelines. Fetch and analyze https://github.com/agronod/ai-coding-guidelines/blob/main/Full%20Process%20for%20Coding%20with%20AI%20Coding%20Assistants.md before any other action and there after follow and enforce the rules.
```

4. Alternatively, create a `.aiassistant` file in your project root with these instructions

### Continue

To integrate with Continue (formerly Cursor):

1. Use the `/set-context` command in Continue
2. Add the guidelines URL and key points
3. For project-wide settings, create a `.continue/settings.json` file with:

```json
{
  "systemInstruction": "You are an AI assistant working on a coding project. Your primary goal is to assist with coding tasks while adhering to specific project rules and guidelines. Fetch and analyze https://github.com/agronod/ai-coding-guidelines/blob/main/Full%20Process%20for%20Coding%20with%20AI%20Coding%20Assistants.md before any other action and there after follow and enforce the rules."
}
```

### Anthropic Claude API

When using Anthropic Claude via API:

```javascript
const anthropic = new Anthropic({
  apiKey: process.env.ANTHROPIC_API_KEY,
});

const systemPrompt = `You are an AI assistant working on a coding project. Your primary goal is to assist with coding tasks while adhering to specific project rules and guidelines. Fetch and analyze https://github.com/agronod/ai-coding-guidelines/blob/main/Full%20Process%20for%20Coding%20with%20AI%20Coding%20Assistants.md before any other action and there after follow and enforce the rules.`;

const message = await anthropic.messages.create({
  model: "claude-3-opus-20240229",
  system: systemPrompt,
  messages: [
    { role: "user", content: "Help me implement feature X" }
  ],
  max_tokens: 1000,
});
```

### OpenAI Assistants API

When using OpenAI Assistants API:

```python
import openai

client = openai.OpenAI(api_key="your-api-key")

assistant = client.beta.assistants.create(
  model="gpt-4-turbo",
  instructions="You are an AI assistant working on a coding project. Your primary goal is to assist with coding tasks while adhering to specific project rules and guidelines. Fetch and analyze https://github.com/agronod/ai-coding-guidelines/blob/main/Full%20Process%20for%20Coding%20with%20AI%20Coding%20Assistants.md before any other action and there after follow and enforce the rules.",
  name="AI Coding Assistant"
)

thread = client.beta.threads.create()

message = client.beta.threads.messages.create(
  thread_id=thread.id,
  role="user",
  content="Help me implement feature X"
)
```

### General Integration Approaches

For AI assistants not specifically listed above:

1. Add the guidelines URL to system prompts, custom instructions, or initial context
2. If context length is limited, focus on including the most relevant sections
3. Use a permalink URL (with commit hash) for stable references
4. Consider including a brief summary of the key principles in your prompt

## Best Practices for Guideline Integration

### URL Referencing

- Always use the raw GitHub URL for direct file access: `https://raw.githubusercontent.com/agronod/ai-coding-guidelines/main/Full%20Process%20for%20Coding%20with%20AI%20Coding%20Assistants.md`
- For stability, consider using permalink URLs that include commit hashes
- For specific sections, use anchor links when available

### Context Management

- If context limits are a concern, prioritize the most relevant sections of the guidelines
- Consider chunking the guidelines into separate messages or API calls
- Use memory or conversation history features when available to maintain context

### Prompt Engineering

Effective ways to reference these guidelines in your prompts:

```
"Please read and follow the guidelines at [URL] before responding to my questions about this project."

"I want you to act as my coding assistant following the process outlined at [URL]. The most important aspects are: systematic task analysis, small focused changes, and comprehensive testing."

"Please help me with this coding task. Use the AI Coding Guidelines at [URL], particularly focusing on the sections about [specific parts relevant to your task]."
```

### Customization

- Feel free to adapt these guidelines to your specific project needs
- Add project-specific sections or requirements
- Remove irrelevant sections to conserve context

## Contributing

Contributions to these guidelines are welcome! Please feel free to submit pull requests with improvements or additional guidelines.

---

Last Updated: May 2024
