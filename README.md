# bmad-custom-workflow

This repository contains custom workflows for the BMAD (Build, Measure, Analyze, Decide) framework, designed to enhance development agility and efficiency. It introduces two key workflows: the **Enhanced Rapid PoC Workflow** and the **Rapid Bug Fix Workflow**.

## 🚀 Enhanced Rapid PoC Workflow

This workflow is designed for rapidly prototyping and iterating on **new projects or significant feature updates**. It streamlines the process by integrating external tools, facilitating interactive research, automating checks, and providing structured documentation.

**Key Features:**
*   **Mode Selection:** Choose between starting a `new` PoC or adding a `feature` to an existing one.
*   **Interactive Research:** Generates a research prompt for external tool usage.
*   **Automated Checks:** Validates and updates package versions.
*   **Structured Documentation:** Organizes generated documentation and validation reports.
*   **Feedback Loops:** Includes pauses for immediate feedback and alignment.

**How to Use:**
1.  Run the `rapid-poc` command.
2.  Follow the interactive prompts to select your mode and proceed through the workflow steps.

## 🐞 Rapid Bug Fix Workflow

This new workflow is dedicated to **quickly identifying and resolving bugs**. It guides developers through leveraging external documentation and internal knowledge bases to analyze, implement, and verify fixes efficiently.

**Key Features:**
*   **Bug Description:** Start by providing a detailed description of the bug.
*   **Leverage Live Docs:** Integrates with Context7 for external documentation and DeepWiki for internal knowledge.
*   **Solution & Implementation:** Assists in analyzing findings, proposing fixes, and guiding through implementation and verification.

**How to Use:**
1.  Run the `rapid-bug-fix` command.
2.  Provide the bug description and follow the guided steps for resolution.

## 🛠️ Integrating into Your Project

This repository includes pre-compiled commands/agents for Claude Code, Cursor, Gemini CLI, and Qwen Code. To integrate these workflows into your own project, copy the `bmad/bmm/workflows/rapid-poc/` and `bmad/bmm/workflows/rapid-bug-fix/` directories into your project's equivalent workflow structure. Ensure your project's `config.yaml` (or similar configuration) is set up to correctly reference `project-root`, `output_folder`, and other variables used within these workflows. Adjust paths or agent names if your project's structure differs.

## 📦 BMAD-METHOD Installation Guide

To install the latest alpha version of the `bmad-method` package, run the following command:
`npx bmad-method@alpha install`

## 📈 Contributing and Feedback

We encourage you to test these workflows extensively and provide your feedback, suggestions, and report any issues. Your input is invaluable for refining and improving these tools.
