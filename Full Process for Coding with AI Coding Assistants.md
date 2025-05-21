# ✅ Full Process for Coding with AI Coding Assistants

This document outlines the enforced and recommended practices for working with AI coding assistants in software development projects.

---

## 🏗️ Project Structure

* Always create a `PLANNING.md` file to outline the project architecture, data flow, and key components.
* Create a `TASK.md` file to track current tasks and their status.
* Maintain a clear folder structure with separate directories for each major component.
* Treat `TASK.md` as the operational truth:

  * Create or update tasks as work begins, progresses, or completes.
  * Reflect dependencies and blockers explicitly.
  * Include a timestamp and author on all entries.

---

## 🧠 AI Behavior Rules

* **Never assume missing context. Ask questions if uncertain.**
* **Never hallucinate libraries or functions** – only use known, verified Python packages.
* **Always confirm file paths and module names** exist before referencing them in code or tests.
* **Never delete or overwrite existing code** unless explicitly instructed to or if part of a task from `TASK.md`.
* **Always validate code**:

  * Ensure syntax correctness and logical accuracy.
  * Run tests or static analysis when applicable.
  * Mention validation results or assumptions explicitly.

---

## 📚 Documentation & Explainability

* **Update `README.md`** when new features are added, dependencies change, or setup steps are modified.
* **Comment non-obvious code** and ensure everything is understandable to a mid-level developer.
* When writing complex logic, **add an inline `# Reason:` comment** explaining the why, not just the what.

---

## 🧪 Testing

* Write **unit tests for every function** using pytest.
* Create **integration tests** for API endpoints and database interactions.
* Write tests that cover **edge cases and error handling**.

---

## 🔍 Code Quality

* Follow **PEP 8** style guidelines for Python code.
* Keep functions **small and focused** on a single responsibility.
* Use **meaningful variable names** that clearly indicate purpose.
* Write **docstrings for every function** using the Google style:

  ```python
  def example():
      """
      Brief summary.

      Args:
          param1 (type): Description.

      Returns:
          type: Description.
      """
  ```

---

## 🧭 Operational Guidelines

* **Sequential Thinking First**

  * Break down problems into logically ordered steps before coding or responding.
  * Document this thought process as part of `PLANNING.md` or `TASK.md`.

* **Maximize Tool Usage**

  * Use all available MCP tools (`sequential-thinking`, `memory`, `context7`) when applicable.
  * Default to tools for validation, coordination, and recall.
  * If unsure, try a tool or ask before proceeding manually.

* **File Indexing and Structure**

  * Use consistent naming.
  * Include component purpose, domain/subsystem, and linked tasks when possible.

---

## ✅ Constraints

* ❌ Do not read `.env` or `.gitignored` files
* ❌ Do not assume availability of secret or environmental configuration unless confirmed
* 📄 Always use and keep `TASK.md` and `PLANNING.md` up to date
* 🤖 Maximize usage of available MCP tools and memory
