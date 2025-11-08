# Rapid PoC Workflow Validation Checklist

This checklist ensures the output of the `rapid-poc` workflow meets the required quality standards for a production-ready Proof of Concept.

## 1. Executable Blueprint Validation

- [ ] **Completeness:** The blueprint addresses all aspects of the initial request.
- [ ] **Research Integration:** Findings from external research (academic papers, web searches) are synthesized into the plan.
- [ ] **Documentation Synthesis:** Insights from user-provided documents (tech specs, internal reports) are correctly incorporated.
- [ ] **Citation:** All claims, patterns, and architectural decisions derived from research are properly cited with links to the source.
- [ ] **Task Decomposition:** The project is broken down into a logical and complete set of tasks.

## 2. Code Implementation Validation

- [ ] **Context-Aware Generation:** Code correctly utilizes `context7 mcp` to fetch and apply the latest API patterns and documentation.
- [ ] **Internal Pattern Adherence:** Code correctly utilizes `deepwiki mcp` to apply established patterns from internal repositories.
- [ ] **Traceability:** Generated code includes inline comments that link directly back to the relevant section of the Executable Blueprint, source documentation, or research paper.
- [ ] **Architectural Compliance:** The generated code structure perfectly matches the architecture defined and approved in the blueprint.
- [ ] **Branching:** All new code has been generated within a new, appropriately named feature branch.

## 3. Testing and Quality Validation

- [ ] **Test Coverage:** A comprehensive test suite has been generated.
- [ ] **Traditional Tests:** The suite includes meaningful unit and integration tests for all relevant components.
- [ ] **Agent Evaluation:** For AI agent components, specialized evaluation frameworks and tests have been created.
- [ ] **Framework Sourcing:** Agent evaluation patterns are correctly sourced from authoritative documentation (e.g., Google ADK docs via `context7 mcp`).
- [ ] **Test Execution:** All generated tests pass successfully without errors.

## 4. Final Output & Commit Validation

- [ ] **Task Status:** All tasks are correctly marked as either 'done' or have their status noted with a logged 'obstacle'.
- [ ] **Commit Integrity:** The final code is committed successfully.
- [ ] **Commit Message:** The commit message is descriptive, summarizes the implemented PoC, and references the version of the Executable Blueprint used.
- [ ] **Readiness:** The final output is in a state ready for the next iteration of development or for peer review.
