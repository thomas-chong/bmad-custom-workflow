# Rapid PoC Workflow Instructions

<critical>The workflow execution engine is governed by: {project-root}/bmad/core/tasks/workflow.xml</critical>
<critical>You MUST have already loaded and processed: {project-root}/bmad/bmm/workflows/rapid-poc/workflow.yaml</critical>
<critical>Communicate in {communication_language} throughout the workflow process</critical>

<workflow>

<step n="0" goal="Workflow Initialization & Pre-flight Check">
  <action>
  Determine if the user intends to start a new Proof of Concept (PoC) from scratch or add a significant feature update to an existing codebase.
  If adding a feature, identify the target branch or prompt the user to create a new 'feat/' branch.
  </action>
  <ask>Are you starting a new PoC (type 'new') or adding a feature to an existing one (type 'feature')? For bug fixes, please use the 'rapid-bug-fix' workflow. If adding a feature, please specify the branch name or type 'new-branch' to create one.</ask>
  <template-output>workflow_mode, target_branch</template-output>
  <action>
  Verify that the '{project-root}' variable is correctly resolved and accessible.
  Check for the existence and readability of all critical workflow files:
  - '{installed_path}/workflow.yaml'
  - '{installed_path}/instructions.md'
  - '{installed_path}/checklist.md'
  If any file is missing or inaccessible, provide a clear error message and guidance to the user.
  </action>
  <ask>Are all critical workflow files accessible and is the environment correctly configured?</ask>
  <template-output>preflight_check_status</template-output>
</step>

<step n="1" goal="AI-Assisted Initiation & Comprehensive Research Prompt Generation" if="workflow_mode == 'new'">
  <action>
  Engage with the user, {user_name}, to understand their high-level idea for the Proof of Concept.
  If the user provides external documents (research papers, tech specs), ingest and analyze their content.
  Based on the initial idea, tech stack, and document analysis, generate a comprehensive research prompt.
  This prompt should be designed to be used with external tools (e.g., web search, arXiv).
  Export the prompt as a markdown file to '{output_folder}/research-prompt.md'.
  </action>
  <template-output>research_prompt_path</template-output>
  <ask>The research prompt has been generated at '{output_folder}/research-prompt.md'. I will now pause and wait for your input. Please execute the research and provide the report in the next message.</ask>
</step>

<step n="2" goal="Receive Research Report">
  <action>
  Wait for the user to provide the research report.
  </action>
  <ask>Please paste the research report here.</ask>
  <template-output>research_report</template-output>
</step>

<step n="3" goal="Ingest Research Report & Elaborate Executable Blueprint">
  <action>
  Ingest the research report provided by the user in the previous step.
  Synthesize the findings from all available sources: user-provided documents, the research report, and real-time documentation from context7 MCP and deepwiki MCP.
  Weave this synthesized knowledge into an initial plan, expanding it into a rich, interactive "Executable Blueprint".
  The blueprint must include not just the plan, but also the citations, references, and production-ready patterns discovered during research.
  </action>
  <template-output>executable_blueprint</template-output>
  <ask>Does the Executable Blueprint accurately reflect the synthesized knowledge and expanded plan?</ask>
</step>

<step n="4" goal="Package Version Validation">
  <action>
  Parse the Executable Blueprint to identify all specified software packages (e.g., from requirements.txt, package.json).
  For each package, use the 'package-version mcp' to query the latest stable version from its respective repository (PyPI, npm).
  Compare the versions specified in the blueprint with the latest available versions.
  If discrepancies are found, update the Executable Blueprint with the latest versions.
  </action>
  <template-output>executable_blueprint_updated</template-output>
  <ask>The package versions in the Executable Blueprint have been validated and updated. Do you approve the changes?</ask>
</step>

<step n="5" goal="Developer Plan Validation & Structured Blueprint Generation">
  <action>
  Present the complete Executable Blueprint to {user_name} for review.
  Facilitate a collaborative refinement session. Answer questions, provide clarifications, and modify the blueprint based on the developer's feedback and expertise.
  This step is an iterative loop that concludes only when the developer formally approves the plan.
  </action>
  <action>
  Upon approval, generate a structured set of documentation in the '{output_folder}':
  - Create the '{output_folder}' if it doesn't exist.
  - Create a subfolder '{output_folder}/details' for detailed documentation if it doesn't exist.
  - Generate '{output_folder}/README.md' for the high-level plan, goals, and architecture.
  - For each identified module, create '{output_folder}/details/module-name.md' with detailed implementation plans.
  - Analyze the blueprint for keywords (e.g., 'AI agent'). If found, create specialized documents like '{output_folder}/details/agent-design.md' with relevant templates.
  </action>
  <ask>The Executable Blueprint has been validated and the structured documentation, including detailed implementation plans, has been generated in the '{output_folder}' folder. Please review the generated documentation. Is it good, or do you have any feedback or modifications?</ask>
  <template-output>validated_blueprint, structured_docs_status</template-output>
</step>

<step n="7" goal="Knowledge-Fueled Implementation">
  <action if="workflow_mode == 'new'">
  Upon plan approval, create a new feature branch (e.g., 'feat/my-new-feature') in the git repository for the PoC.
  </action>
  <action if="workflow_mode == 'feature'">
  Upon plan approval, switch to the '{target_branch}' or create it if 'new-branch' was specified.
  </action>
  <action>
  Generate the complete code structure and files as defined in the validated blueprint.
  The code generation process must be knowledge-fueled, actively using context7 MCP for the latest API patterns and deepwiki MCP for existing internal patterns.
  Embed references directly into the code as inline comments, including links to docs, research citations, and tech spec notes.
  </action>
  <template-output>generated_code, branch_name</template-output>
  <ask>Has the code been generated successfully in the new feature branch, and does it align with the validated blueprint?</ask>
</step>

<step n="7" goal="Developer Code Validation">
  <action>
  Present the generated code to {user_name} for their expert review.
  The code should be clean, well-structured, and directly traceable to the blueprint via its inline citations.
  Allow the developer to make final adjustments or request modifications.
  </action>
  <action>
  Generate a comprehensive code validation report, detailing code quality, adherence to blueprint, and any identified areas for improvement.
  Create a subfolder '{output_folder}/details/validation' if it doesn't exist.
  Save the report as '{output_folder}/details/validation/code-validation-report.md'.
  </action>
  <template-output>validated_code, code_validation_report_path</template-output>
  <ask>Have you reviewed and approved the generated code, and are there any further modifications required? The code validation report is available at '{output_folder}/details/validation/code-validation-report.md'.</ask>
</step>

<step n="8" goal="Specialized Test Generation">
  <action>
  Generate a comprehensive test suite for the validated code.
  This suite must include traditional unit and integration tests.
  Crucially, it must also include specialized AI agent evaluations. Use context7 MCP to fetch the latest evaluation frameworks and patterns from relevant documentation (e.g., Google ADK docs).
  </action>
  <template-output>test_suite</template-output>
  <ask>Has the comprehensive test suite been generated, including traditional and specialized AI agent evaluations?</ask>
</step>

<step n="9" goal="Task Resolution, Obstacle Tracking & Commit">
  <action>
  Execute the full test suite against the validated code.
  If all tests pass, perform the final commit to the feature branch with a detailed, descriptive commit message summarizing the work.
  Mark the completed tasks as 'done' in the workflow's internal state.
  If any tasks are incomplete or have issues, log them as obstacles for the next iteration.
  Conclude by summarizing the results for {user_name} and preparing for the next development cycle.
  </action>
  <template-output>commit_hash, task_status, obstacles_log</template-output>
  <ask>Have all tests passed, and has the final code been committed successfully with a descriptive message?</ask>
</step>

</workflow>
