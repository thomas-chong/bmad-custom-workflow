# Rapid PoC Workflow

## Overview

The `rapid-poc` workflow is a powerful, intent-driven meta-workflow designed to accelerate the creation of high-quality, production-ready Proofs of Concept (PoCs). It enables developers to go from a high-level idea to a validated, tested, and committed codebase in a fraction of the time required by traditional methods.

The core of this workflow is the **Executable Blueprint**: a rich, interactive, and intelligent specification that is generated dynamically based on the user's idea, existing documentation, and real-time research.

## How to Invoke

This workflow is `standalone` and can be invoked directly from the command line or your IDE's command palette:

`/workflow rapid-poc`

## The 7-Step Process

The workflow guides the developer through a 7-step, medium-interactivity process:

1.  **AI-Assisted Initiation & Research Planning:** Generates a high-level plan and targeted research prompts from the initial idea and any uploaded documents.
2.  **Executable Blueprint Elaboration:** Executes research and synthesizes findings from all sources (user docs, academic papers, `context7` MCP, `deepwiki` MCP) into the interactive blueprint.
3.  **Developer Plan Validation:** A crucial interactive checkpoint where the developer reviews, refines, and approves the Executable Blueprint.
4.  **Knowledge-Fueled Implementation:** Generates the complete, well-commented code in a new feature branch, based on the validated blueprint.
5.  **Developer Code Validation:** A second interactive checkpoint for the developer to review and approve the generated code.
6.  **Specialized Test Generation:** Autonomously creates a comprehensive test suite, including traditional tests and specialized AI agent evaluations.
7.  **Task Resolution & Commit:** Runs all tests, commits the final code, and logs the status of all tasks, preparing for the next iteration.

## Required Tools

This workflow requires the following MCP tools to be available:

*   **context7 mcp:** For fetching the latest documentation from external sources.
*   **deepwiki mcp:** For retrieving patterns and knowledge from internal repositories.

## When to Use

Use this workflow when you need to:

*   Quickly prototype a new feature or application.
*   Ensure a new concept is grounded in best practices and existing research.
*   Develop a PoC that requires integration with internal systems or complex external APIs.
*   Maintain high code quality and test coverage even under tight deadlines.
