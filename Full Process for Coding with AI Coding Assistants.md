# @ai-ruleset
# Full Process for Coding with AI Coding Assistants

## 🧠 Core Principles

### 1. Sequential Thinking
- Always break down tasks into discrete, logical steps
- Document your thought process before writing code
- Use tools like `sequential-thinking` when available to structure complex tasks

### 2. Tool Utilization
- Maximize use of available MCP tools (context7, memory, filesystem)
- Always verify file paths and module names before referencing
- Use code search and analysis tools to understand the codebase

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
- Write tests for all new functionality
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
   - Search existing codebase for similar implementations

2. **Plan Implementation**
   - Break down into subtasks
   - Identify potential challenges
   - Choose appropriate tools and libraries

3. **Implement**
   - Make small, testable changes
   - Verify each step
   - Document decisions

4. **Review**
   - Check against requirements
   - Run tests
   - Get feedback

5. **Deploy**
   - Update documentation
   - Monitor after deployment
   - Gather metrics
