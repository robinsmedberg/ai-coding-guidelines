# @ai-ruleset
# Full Process for Coding with AI Coding Assistants

## 🧠 Core Principles

### 1. Sequential Thinking
- Always break down tasks into discrete, logical steps
- Document your thought process before writing code
- Use `sequential-thinking` tool to structure complex tasks
- For process-related questions, always demonstrate tool usage
- Include thought process in responses when explaining approaches

### 2. Tool Utilization
- Maximize use of available MCP tools (context7, memory, filesystem)
- Always verify file paths and module names before referencing
- Use code search and analysis tools to understand the codebase
- Follow the Tool Selection Matrix for appropriate tool usage
- Document tool usage in responses when relevant

## 🏗️ Project Structure
- Maintain a `PLANNING.md` for architecture and data flow
- Keep `TASK.md` updated with current tasks and status
- Use clear, consistent directory structure
- Document all environment variables in `.env.example`

## 🛠️ Development Workflow

### 1. Planning Phase
- Use `sequential-thinking` to break down requirements
- Document all assumptions and decisions
- Update `PLANNING.md` with technical specifications

### 2. Implementation
- Make small, focused changes
- Use version control effectively
- Follow the Single Responsibility Principle

### 3. Verification
- Run tests after each change
- Validate against requirements
- Check for regressions

## 🧪 Testing Strategy
- Ask if tests should be implemented
- Include edge cases and error conditions
- Use mocking for external dependencies
- Maintain test data in a separate directory

## 📚 Documentation
- Keep `README.md` updated
- Document complex logic with `# Reason:` comments
- Include examples for API usage
- Maintain a changelog

## 🔄 MCP Integration
- Use MCP tools for:
  - Code search and analysis
  - Documentation lookup
  - File system operations
  - Memory and context management

## 🎯 Tool Usage and Response Protocols

### Tool Selection Matrix
| Question Type          | Primary Tool          | Secondary Tools        | When to Use                     |
|------------------------|-----------------------|------------------------|---------------------------------|
| Process/Approach       | sequential-thinking   | context7              | Explaining approaches, planning |
| Code Location          | codebase_search       | grep_search           | Finding code in the codebase    |
| File Contents          | view_file             | list_dir              | Viewing file contents           |
| External Knowledge     | context7              | web_search            | Looking up documentation       |
| Project Structure      | list_dir              | find_by_name          | Exploring project layout        |
| Data Analysis          | sequential-thinking   | context7              | Analyzing data or requirements  |

### Pre-Response Checklist
1. [ ] Determine if question requires tool usage
2. [ ] Select appropriate tool(s) from matrix
3. [ ] Execute tool with proper parameters
4. [ ] Incorporate tool output into response
5. [ ] Verify response addresses original question

### Default Actions
- When in doubt, default to `sequential-thinking`
- If no tool seems appropriate, state which tools were considered and why they weren't used
- For ambiguous cases, ask clarifying questions before proceeding

## ✅ Quality Assurance
- Follow language style guides
- Use linters and formatters
- Conduct code reviews
- Monitor performance

## 🚀 Deployment
- Containerize applications
- Document deployment process
- Include health checks
- Monitor in production

## 🔍 Continuous Improvement
- Regularly update dependencies
- Refactor when necessary
- Learn from production issues
- Incorporate feedback

# Example Sequential Thinking Process

When approaching a task:

1. **Analyze Requirements**
   - Use `context7` to gather relevant documentation
   - Search existing codebase using `codebase_search`
   - Verify file paths with `list_dir` or `find_by_name`

2. **Plan Implementation**
   - Use `sequential-thinking` to break down the task
   - Document thought process and decisions
   - Reference relevant guideline sections

3. **Implement**
   - Make small, testable changes
   - Verify each step using appropriate tools
   - Document decisions with `# Reason:` comments

4. **Review**
   - Check against requirements using verification tools
   - Run tests and verify outputs
   - Use self-monitoring checklist

5. **Deploy & Document**
   - Update documentation with changes
   - Include tool usage in documentation
   - Monitor and gather metrics

## 🧐 Self-Monitoring
- After each response, verify:
  - All applicable tools were used
  - Tool outputs were properly incorporated
  - Response follows guidelines
  - No assumptions were made without verification
  - Complex logic is documented with `# Reason:` comments

## 🔄 Error Recovery
- If a tool fails:
  1. Document the attempt
  2. Try alternative tools if available
  3. If no tools are suitable, explain why and ask for guidance
- For unclear situations, default to asking clarifying questions
