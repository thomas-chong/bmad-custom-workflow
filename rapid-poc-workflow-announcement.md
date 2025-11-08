*🚀 Introducing the Enhanced Rapid PoC Workflow and the NEW Rapid Bug Fix Workflow! 🚀*

Hey team!

We've supercharged our `rapid-poc` workflow and introduced a brand new `rapid-bug-fix` workflow to address some of the pain points with traditional BMAD, especially around speed and iteration. These updated workflows are designed to help us rapidly prototype and iterate on ideas, features, and *efficiently address bugs*.

*💡 Motivation: Why the change?*
Traditional BMAD workflows can sometimes feel a bit slow, especially when you're in a rapid prototyping phase or need to quickly address an issue. This enhanced `rapid-poc` workflow aims to cut down on friction by integrating external tools and making the process more interactive and iterative for *new projects and feature development*. For *bug fixes*, we now have a dedicated, streamlined workflow.

*🛠️ How to Use the New Workflows:*

*For New Projects & Feature Updates (Rapid PoC Workflow):*
You can now kick off the `rapid-poc` workflow for *new projects* or to *add significant feature updates* to existing ones using the same command!

1.  *Start the Workflow:* Run the `rapid-poc` command.
2.  *Choose Your Mode:* The workflow will first ask if you're starting a `new` PoC or `feature` for an existing one.
    *   If `new`, it proceeds with a fresh project.
    *   If `feature`, it will prompt you for a target branch or to create a new `feat/` branch.
3.  *Interactive Research:* The workflow will generate a comprehensive research prompt (saved to `docs/research-prompt.md`). You'll then use your preferred external tools to conduct the research and provide the report back to the workflow.
4.  *Automated Checks:* It will automatically validate and update package versions (npm/PyPI) in your blueprint.
5.  *Structured Documentation:* All generated documentation, including detailed implementation plans, will now be neatly organized in `docs/details/` with a code validation report in `docs/details/validation/`.
6.  *Feedback Loops:* We've added explicit pauses at key stages, like after documentation generation, to get your immediate feedback and ensure alignment.

*For Bug Fixes (Rapid Bug Fix Workflow):*
Use the new `rapid-bug-fix` workflow for quickly identifying and resolving bugs.

1.  *Start the Workflow:* Run the `rapid-bug-fix` command.
2.  *Bug Description:* Provide a detailed description of the bug.
3.  *Leverage Live Docs:* The workflow will guide you through querying Context7 for external documentation and DeepWiki for internal knowledge.
4.  *Solution & Implementation:* It will help analyze findings, propose a fix, and guide you through the implementation and verification steps.

*Applying this repo to your own project:*
This repository includes pre-compiled commands/agents for Claude Code, Cursor, Gemini CLI, and Qwen Code. To integrate these workflows into your own project, you can copy the `bmad/bmm/workflows/rapid-poc/` and `bmad/bmm/workflows/rapid-bug-fix/` directories into your project's equivalent workflow structure. Ensure your project's `config.yaml` (or similar configuration) is set up to correctly reference the `project-root`, `output_folder`, and other variables used within these workflows. You may need to adjust paths or agent names if your project's structure differs significantly.

*📈 How to Improve It:*
This is a big step towards a more agile BMAD experience! We need your help to make it even better. Please *test these workflows extensively* for both new projects, feature additions, and bug fixes.

Share your feedback, suggestions, and any issues you encounter. Your input is crucial for refining these workflows and making them powerful tools for everyone.

Let's build amazing things, faster!

---

*BMAD-METHOD Installation Guide:*
To install the latest alpha version of the `bmad-method` package, run the following command:
`npx bmad-method@alpha install`