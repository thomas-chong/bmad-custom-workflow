<critical>The workflow execution engine is governed by: {project_root}/bmad/core/tasks/workflow.xml</critical>
<critical>You MUST have already loaded and processed: workflow.yaml</critical>

<workflow>

  <step n="1" goal="Understand the Bug">
    <action>Engage in collaborative discovery to fully understand the reported bug.

    Ask open-ended questions to explore:
    - What is the exact problem?
    - What are the steps to reproduce it?
    - What is the expected behavior vs. actual behavior?
    - What is the impact of the bug?
    - When did it start occurring?
    - What changes were recently deployed that might be related?

    Listen for clues about:
    - Error messages or logs
    - Specific user actions
    - Environment details (browser, OS, device)
    - Related features or components

    Adapt your depth and terminology to the user's responses.
    If they give brief answers, dig deeper with follow-ups.
    If they're uncertain, help them think through it with examples.
    </action>
    <template-output>bug_description</template-output>
  </step>

  <step n="2" goal="Query Context7 for External Documentation">
    <action>Formulate and execute accurate queries against Context7 to find relevant external documentation.

    Consider search terms based on:
    - Error messages
    - Technologies involved (frameworks, libraries, APIs)
    - General problem descriptions
    - Best practices for the affected area

    Generate multiple, varied queries to ensure comprehensive coverage.
    Analyze the search results for official documentation, community discussions, and known solutions.
    </action>
    <template-output>context7_findings</template-output>
  </step>

  <step n="3" goal="Query DeepWiki for Internal Documentation">
    <action>Formulate and execute accurate queries against DeepWiki to find relevant internal documentation and code patterns.

    Consider search terms based on:
    - Internal project names or modules
    - Specific function or class names
    - Past bug reports or design documents
    - Team-specific conventions or solutions

    Generate multiple, varied queries to ensure comprehensive coverage.
    Analyze the search results for internal wikis, code snippets, architectural decisions, and previous fixes.
    </action>
    <template-output>deepwiki_findings</template-output>
  </step>

  <step n="4" goal="Analyze Findings and Propose Solution">
    <action>Synthesize the information gathered from Context7 and DeepWiki.

    Identify:
    - Root cause of the bug
    - Potential solutions or workarounds
    - Impact of proposed changes
    - Any known side effects or dependencies

    Propose a detailed plan for fixing the bug, including:
    - Specific code changes
    - Configuration updates
    - Testing strategy
    - Rollback plan (if necessary)
    </action>
    <template-output>proposed_fix_plan</template-output>
  </step>

  <step n="5" goal="Implement the Fix">
    <action>Guide the user through the implementation of the proposed fix.

    Provide clear, step-by-step instructions for:
    - Modifying code files
    - Updating configurations
    - Running local tests

    Offer assistance with debugging or refining the implementation as needed.
    </action>
    <template-output>implemented_code_changes</template-output>
  </step>

  <step n="6" goal="Verify the Fix">
    <action>Collaborate with the user to verify that the bug has been successfully resolved and no new issues were introduced.

    Guide through:
    - Re-running the steps to reproduce the original bug
    - Executing relevant unit, integration, and end-to-end tests
    - Performing regression testing on related functionalities
    - Checking logs for new errors or warnings

    Confirm that the expected behavior is now observed and the system remains stable.
    </action>
    <template-output>verification_report</template-output>
  </step>

</workflow>