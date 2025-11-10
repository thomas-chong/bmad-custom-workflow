# Technical Blog Creator - Workflow Instructions

<critical>The workflow execution engine is governed by: {project-root}/bmad/core/tasks/workflow.xml</critical>
<critical>You MUST have already loaded and processed: {project-root}/bmad/bmm/workflows/technical-blog-creator/workflow.yaml</critical>
<critical>Communicate in {communication_language} throughout the entire workflow</critical>

<workflow>

<!-- ============================================ -->
<!-- PHASE 1: PLANNING & STRUCTURE -->
<!-- ============================================ -->

<step n="1" goal="Gather topic, content type, and initial references">
<action>Greet {user_name} and explain this workflow creates comprehensive technical blog posts with working code, visual aids, and human-quality writing</action>

<action>Gather essential information through conversation:

**Topic & Content Type:**
- What technical topic do you want to write about?
- What type of content is this?
  - Academic paper summary
  - Step-by-step tutorial
  - New feature highlight
  - Technical demo
  - Other (let user specify)

**Target Audience:**
- Who is the primary audience? (AI Engineers, MLEs, SWEs, AI Researchers, or other)
- What's their assumed technical level? (Beginner, Intermediate, Advanced)

**Initial References:**
- Do you have any starting references? (URLs, documents, papers, repos)
- Any existing code or examples to build from?

Adapt your questions to the user's responses - if they provide lots of detail upfront, acknowledge it and ask clarifying follow-ups instead of repeating questions.
</action>

<action>Create a topic slug for file naming (lowercase, hyphens, no spaces)</action>

<template-output>topic</template-output>
<template-output>topic_slug</template-output>
<template-output>content_type</template-output>
<template-output>target_audience</template-output>
<template-output>technical_level</template-output>
<template-output>initial_references</template-output>
</step>

<step n="2" goal="Create detailed content plan with subsections and placeholders">
<action>Explain you'll now create a comprehensive content plan that maps out the entire blog structure</action>

<action>Based on the topic, content type, and target audience, design a detailed content plan with:

**High-Level Structure:**
- Introduction (hook, problem statement, overview)
- Main sections (3-6 major sections appropriate for the content type)
- Conclusion (key takeaways, next steps, resources)

**Subsection Breakdown:**
For each major section, define 2-4 subsections with:
- Specific topics to cover
- Content type indicators: [CODE], [DIAGRAM], [SCREENSHOT], [TABLE], [EXAMPLE]
- Estimated depth/length

**Visual Content Planning:**
Identify where visual aids are needed:
- Architecture diagrams (use Mermaid)
- Flowcharts or sequence diagrams
- Screenshots (UI, terminal, browser)
- Comparison tables
- Code examples with output

**Tone and Style:**
- Maintain human, authentic voice
- Balance technical depth with accessibility
- Include personal insights or opinions where appropriate
- Avoid generic AI-generated phrases
</action>

<action>Present the content plan to the user and ask for feedback:
- Are all important topics covered?
- Should any sections be added, removed, or reorganized?
- Is the depth appropriate for the target audience?

Iterate on the plan until the user is satisfied.
</action>

<template-output>content_plan</template-output>
</step>

<step n="3" goal="Generate implementation plan if codebase demo needed">
<ask>Does this blog post require a working code demonstration or tutorial implementation? [yes/no]</ask>

<check if="yes">
  <action>Create a detailed implementation plan:

**Technology Stack:**
- Programming language(s) (Python, JavaScript/TypeScript, Go, Rust, etc.)
- Key frameworks and libraries
- Development environment requirements

**Project Structure:**
- Folder/file organization
- Configuration files needed
- Dependencies (requirements.txt, package.json, etc.)

**Implementation Phases:**
Break the implementation into logical phases:
1. Project setup and scaffolding
2. Core functionality implementation
3. Advanced features (if applicable)
4. Testing approach
5. Deployment considerations (if relevant)

**Code Quality:**
- Include comments explaining key concepts
- Add error handling and best practices
- Create runnable, tested examples (not just snippets)
- Ensure code is beginner-friendly if targeting that audience

**Testing Strategy:**
- How will the user test the implementation?
- What outputs/artifacts should they collect?
- Any specific test cases or scenarios?
  </action>

  <action>Review the implementation plan with the user:
- Does this cover everything needed for the demo?
- Are the phases appropriate?
- Any specific libraries or approaches they want to use?

Refine based on feedback.
  </action>

  <template-output>implementation_plan</template-output>
  <template-output>requires_implementation</template-output>
</check>

<check if="no">
  <action>Note that no code implementation is needed - this is a conceptual or summary piece</action>
  <template-output>requires_implementation</template-output>
</check>
</step>

<!-- ============================================ -->
<!-- PHASE 2: RESEARCH & KNOWLEDGE GATHERING -->
<!-- ============================================ -->

<step n="4" goal="Generate comprehensive deep research prompt">
<action>Explain you'll now create a detailed research prompt for external deep research services (Perplexity, Claude with web search, etc.)</action>

<action>Generate a comprehensive research prompt (500-1000 words) that includes:

**Context Section:**
- Topic overview and background
- Target audience and their needs
- Purpose of the blog post
- Content type and format

**Specific Research Questions:**
Create 8-12 targeted research questions covering:
- Technical foundations and principles
- Current state of the art
- Practical applications and use cases
- Common challenges and solutions
- Best practices and recommendations
- Recent developments or trends
- Comparison with alternatives (if applicable)
- Real-world examples or case studies

**Depth Requirements:**
- Specify the level of technical detail needed
- Areas requiring code examples or APIs
- Any specific papers, repos, or projects to investigate

**Output Format:**
Request the research report to be organized by:
- Executive summary
- Detailed findings per research question
- Code examples and references
- Links to documentation and resources
- Gaps or areas needing more investigation

Make the prompt clear, specific, and actionable for the external research service.
</action>

<action>Present the research prompt to the user and explain:
- Copy this prompt to your preferred deep research service
- Run the research and obtain a comprehensive report
- Return here when you have the research results

If they want to adjust the research prompt, iterate until satisfied.
</action>

<template-output>deep_research_prompt</template-output>
</step>

<step n="5" goal="User executes external research and provides report">
<ask>Please run the deep research using your preferred service (Perplexity, Claude with web search, custom tool, etc.) and paste the research report here when ready.</ask>

<action>Wait for user to provide the research report</action>

<action>Once received, analyze the research report:
- Acknowledge receipt and thank the user
- Identify key findings relevant to each content plan section
- Note any particularly valuable insights or examples
- Flag any gaps that need additional investigation
</action>

<template-output>research_report</template-output>
</step>

<step n="6" goal="Query MCP services for technical documentation">
<action>Explain you'll now gather technical documentation from MCP services to supplement the research</action>

<action>Based on the content plan and implementation plan (if applicable), identify:

**Libraries and Frameworks Needed:**
- What libraries are mentioned in the topic or implementation plan?
- Which frameworks or tools require documentation?

**Repository Documentation:**
- Are there specific open-source projects to reference?
- Which repos have relevant wikis or documentation?

Create a list of MCP queries to run.
</action>

<action>Execute MCP queries:

**For Library Documentation (context7 MCP):**
- Query context7 for API references
- Get usage examples and best practices
- Retrieve relevant code patterns

**For Repository Wikis (deepwiki MCP):**
- Query deepwiki for public repo wikis
- Extract relevant documentation sections
- Get architecture and design patterns

For each query, capture:
- Source (library/repo name)
- Relevant sections
- Code examples
- Best practices or gotchas
</action>

<action>Organize all MCP findings by content plan sections:
- Map each finding to relevant section(s)
- Highlight code examples for integration
- Note any conflicts with research report (resolve if needed)
</action>

<template-output>mcp_documentation</template-output>
</step>

<step n="7" goal="Organize all research findings by content sections">
<action>Create a comprehensive research synthesis:

**For Each Content Plan Section:**
1. List relevant findings from research report
2. List relevant MCP documentation
3. Identify available code examples
4. Note gaps or areas needing clarification

**Create Knowledge Base:**
Organize all gathered information into a structured format:
- Key concepts and definitions
- Technical details and specifications
- Code examples and patterns
- Visual aid requirements
- References and citations

This synthesis will be the foundation for content creation.
</action>

<action>Review the research synthesis with the user:
- Does this cover all needed information?
- Are there any gaps requiring additional research?
- Any areas that need deeper investigation?

If gaps exist, either:
- Run additional MCP queries
- Suggest targeted follow-up research
- Note as "user will provide" for implementation phase
</action>

<template-output>research_synthesis</template-output>
</step>

<!-- ============================================ -->
<!-- PHASE 3: IMPLEMENTATION (Optional) -->
<!-- ============================================ -->

<step n="8" goal="Create complete codebase structure and implementation" if="requires_implementation == true">
<action>Explain you'll now create the complete working codebase based on the implementation plan</action>

<action>Generate the full project structure:

**1. Create Directory Structure:**
- Main project folder
- Source code directories
- Configuration directories
- Test directories (if applicable)
- Assets/resources directories

**2. Generate Dependency Files:**
- requirements.txt (Python)
- package.json (JavaScript/TypeScript)
- go.mod (Go)
- Cargo.toml (Rust)
- Or equivalent for chosen language

**3. Create Configuration Files:**
- .gitignore
- README.md with setup instructions
- Environment configuration (.env.example)
- Any framework-specific config files

**4. Implement Core Functionality:**
Generate code files with:
- Clear, well-commented code
- Proper error handling
- Best practices for the language/framework
- Modular, maintainable structure

**5. Add Examples and Tests:**
- Example usage scripts
- Test files or testing instructions
- Sample data (if needed)

Ensure all code is:
- Runnable without errors
- Well-documented with comments
- Following language conventions
- Appropriate for the target audience's skill level
</action>

<action>Present the complete codebase to the user:
- Show the full directory structure
- Highlight key files and their purpose
- Provide setup instructions

Ask: "Review the codebase structure. Does this look good, or should any adjustments be made?"

Iterate if needed.
</action>

<action>Write all code files to {output_folder}/blog-code-{{topic_slug}}/</action>

<template-output>codebase_structure</template-output>
<template-output>implementation_code</template-output>
<template-output>setup_instructions</template-output>
</step>

<step n="9" goal="User tests implementation and collects artifacts" if="requires_implementation == true">
<action>Instruct the user to test the implementation:

**Testing Steps:**
1. Follow the setup instructions
2. Run the code and verify it works
3. Test key functionality
4. Collect artifacts during testing:
   - Terminal output (copy relevant logs)
   - Screenshots (application UI, results, outputs)
   - Generated files or data
   - Any errors encountered (for troubleshooting section)

**What to Capture:**
- Successful execution screenshots
- Interesting or important outputs
- Step-by-step process images (for tutorials)
- Final results or visualizations
</action>

<ask>Please test the implementation and collect artifacts. When ready, provide:
1. Confirmation that the code works (yes/no)
2. Any artifacts you've collected (paste text outputs, upload images)
3. Any issues encountered

If the code doesn't work, we'll debug and fix it before proceeding.
</ask>

<action>Wait for user feedback and artifacts</action>

<check if="code doesn't work">
  <action>Debug the issues:
  - Review error messages
  - Identify the problem
  - Fix the code
  - Ask user to test again
  </action>
  <goto step="9">Retry testing after fixes</goto>
</check>

<check if="code works">
  <action>Collect and organize all user-provided artifacts:
  - Save text outputs
  - Reference image locations
  - Note any interesting findings from testing
  </action>
  <template-output>test_artifacts</template-output>
</check>
</step>

<step n="10" goal="Generate and collect visual aids" if="requires_implementation == true">
<ask>For browser-based demos, would you like to use automated screenshot/demo capture via chrome-devtools MCP? [yes/no/not-needed]</ask>

<check if="yes">
  <action>Use chrome-devtools MCP to automate browser interactions:

**Automated Capture Steps:**
1. Identify URL(s) or pages to demo
2. Define interaction sequence (clicks, inputs, navigation)
3. Specify screenshot points
4. Execute automation and capture results

**For Each Demo Scenario:**
- Navigate to starting point
- Perform actions (form inputs, button clicks, etc.)
- Capture screenshots at key moments
- Save resulting images

Store all automated screenshots with descriptive names.
  </action>
  <template-output>automated_screenshots</template-output>
</check>

<check if="no">
  <action>Ask user to provide any additional screenshots manually if needed</action>
  <action>Note that manual screenshots have been provided (or will be integrated later)</action>
</check>

<action>Compile complete visual asset inventory:
- User-provided screenshots
- Automated screenshots (if applicable)
- Terminal outputs
- Diagrams to be generated (defer to next step)
- Tables to be created

Create a visual content map showing where each asset fits in the content plan.
</action>

<template-output>visual_assets_inventory</template-output>
</step>

<!-- Skip steps 8-10 if no implementation needed -->

<!-- ============================================ -->
<!-- PHASE 4: CONTENT CREATION -->
<!-- ============================================ -->

<step n="11" goal="Draft complete blog content with all gathered context">
<action>Announce that you'll now draft the complete blog post using all gathered information</action>

<critical>Writing Quality Requirements:

**MUST HAVE:**
- Human, authentic voice (not robotic AI-generated text)
- Concrete examples and specific details
- Natural sentence variety (not formulaic patterns)
- Technical insights with depth
- Personal perspective or opinion where appropriate

**MUST AVOID (AI Slop Indicators):**
- Generic openings ("In today's fast-paced world...")
- Overused transitions ("Moreover", "Furthermore" in every paragraph)
- Vague statements without evidence
- Repetitive sentence structures
- Buzzwords without substance
- Surface-level explanations

**Writing Style:**
- Direct and conversational
- Technical but accessible
- Engaging and informative
- Backed by evidence and examples
</critical>

<action>Draft the complete blog post following the content plan:

**For Each Section:**

1. **Introduction:**
   - Engaging hook that draws readers in
   - Clear problem statement or motivation
   - Brief overview of what readers will learn
   - Personal context or why this topic matters

2. **Main Sections:**
   For each major section from the content plan:
   - Write clear, detailed content
   - Integrate research findings naturally
   - Include code examples from implementation (if applicable)
   - Reference MCP documentation where relevant
   - Add placeholders for visuals: `[DIAGRAM: description]`, `[SCREENSHOT: description]`, `[TABLE: description]`
   - Use subheadings for subsections
   - Maintain consistent technical depth

3. **Code Examples:**
   - Include syntax highlighting (specify language)
   - Add comments explaining key concepts
   - Show both code and output
   - Provide context before and after each example

4. **Conclusion:**
   - Summarize key takeaways (3-5 bullet points)
   - Suggest next steps or further reading
   - Include relevant resources and links
   - Optional: Personal reflection or future directions

**Formatting:**
- Use markdown syntax
- Proper heading hierarchy (h1, h2, h3)
- Code blocks with language tags
- Lists and emphasis where appropriate
- Clear paragraph breaks
</action>

<action>Review the drafted content yourself:
- Does it flow naturally?
- Are explanations clear and complete?
- Is the writing human and engaging (not AI slop)?
- Are all content plan sections addressed?

Make initial improvements before showing to user.
</action>

<action>Create a comprehensive references and resources section:
- List all research sources used
- Include MCP documentation links
- Add relevant external resources
- Provide links to libraries, frameworks, tools mentioned
- Include links to any referenced papers or articles
</action>

<template-output>blog_draft</template-output>
<template-output>references_section</template-output>
</step>

<step n="12" goal="Generate and integrate visual elements">
<action>Now create all visual aids for the blog post</action>

<action>Generate diagrams using Mermaid syntax:

**For Each Diagram Placeholder:**
1. Identify diagram type needed (flowchart, sequence, architecture, etc.)
2. Create Mermaid diagram code
3. Add descriptive caption
4. Note placement in content

**Common Diagram Types:**
- Architecture diagrams (graph/flowchart)
- Sequence diagrams (interaction flows)
- Flowcharts (process flows)
- Class diagrams (OOP structure)
- Entity-relationship diagrams (data models)

Generate clear, well-labeled diagrams that enhance understanding.
</action>

<action>Create tables for comparisons, feature matrices, or API references:

**For Each Table Placeholder:**
1. Structure data clearly in markdown table format
2. Include headers
3. Ensure alignment and readability
4. Add caption/description

Tables should be:
- Well-organized
- Easy to scan
- Properly formatted in markdown
</action>

<action>Update the blog draft to replace all placeholders:
- Insert Mermaid diagram code blocks
- Insert markdown tables
- Reference screenshot locations (user-provided or automated)
- Add image markdown syntax: `![Alt text](image-path)`

Ensure all visual elements are properly integrated and referenced in the text.
</action>

<template-output>diagrams</template-output>
<template-output>tables</template-output>
<template-output>blog_content_with_visuals</template-output>
</step>

<!-- ============================================ -->
<!-- PHASE 5: QUALITY VALIDATION & PUBLISHING -->
<!-- ============================================ -->

<step n="13" goal="Self-reflection and comprehensive quality validation">
<action>Conduct thorough quality assessment of the blog content</action>

<critical>Quality Validation Criteria:

**1. Technical Accuracy:**
- [ ] All code examples are syntactically correct and runnable
- [ ] Technical claims are accurate and verifiable
- [ ] Library/API references are current and correct
- [ ] Examples match implementation (if applicable)

**2. Content Completeness:**
- [ ] All content plan sections are addressed
- [ ] All visual aids are present and integrated
- [ ] Code examples have sufficient context
- [ ] Links and references are included

**3. Readability and Flow:**
- [ ] Logical section progression
- [ ] Clear transitions between topics
- [ ] Appropriate technical depth for audience
- [ ] Consistent terminology throughout
- [ ] Sentence length varies (not repetitive)
- [ ] Paragraphs are focused and cohesive

**4. AI Slop Detection (CRITICAL):**
- [ ] NO generic openings ("In today's fast-paced world...")
- [ ] NO overused transitions (repetitive "Moreover", "Furthermore")
- [ ] NO vague statements without concrete examples
- [ ] NO formulaic sentence patterns
- [ ] NO buzzwords without substance
- [ ] YES to specific, concrete details
- [ ] YES to personal insights or opinions
- [ ] YES to authentic, human voice
- [ ] YES to technical depth and nuance

**5. Visual Quality:**
- [ ] Diagrams are clear and informative
- [ ] Screenshots are relevant and well-captioned
- [ ] Tables are properly formatted
- [ ] Visual aids enhance understanding
- [ ] Sufficient visual variety

**6. Engagement and Value:**
- [ ] Hook captures attention
- [ ] Content provides real value
- [ ] Examples are practical and useful
- [ ] Conclusion provides clear takeaways
- [ ] Readers can take action based on content
</critical>

<action>Perform the quality assessment:

For each criterion above:
1. Review the content thoroughly
2. Identify any issues or gaps
3. Note specific improvements needed
4. Prioritize by severity (critical, important, nice-to-have)

Create a quality assessment report with:
- Overall assessment (ready to publish / needs minor refinement / needs major revision)
- Critical issues (must fix)
- Important improvements (should fix)
- Optional enhancements (could fix)
- Specific examples of AI slop detected (if any)
</action>

<action>Present the quality assessment to the user:

"I've completed a quality review of the blog post. Here's my assessment:

**Overall Status:** [ready/minor refinement needed/major revision needed]

**Strengths:**
- [List 3-5 strong points]

**Issues Found:**
[List any issues with specific examples and suggested fixes]

**AI Slop Check:**
[Report on human-like writing quality, flag any formulaic patterns]

Would you like me to address these issues automatically, or would you prefer to review them first?"
</action>

<template-output>quality_assessment</template-output>
</step>

<step n="14" goal="Refinement loop and finalization" repeat="until-satisfied">
<ask>Based on the quality assessment, what would you like to do?

1. Auto-fix all issues and regenerate content
2. Let me review and provide specific feedback
3. Content looks good, proceed to output generation

Enter 1, 2, or 3:
</ask>

<check if="option 1 - auto-fix">
  <action>Automatically address all identified issues:
  - Rewrite sections with AI slop indicators
  - Fix technical inaccuracies
  - Improve transitions and flow
  - Enhance visual integration
  - Strengthen conclusion and takeaways

  Regenerate the affected sections with improvements.
  </action>
  <action>Show updated content to user and ask for approval</action>
</check>

<check if="option 2 - user feedback">
  <action>Ask user for specific feedback:
  - What sections need work?
  - What improvements do they want?
  - Any additional content to add?
  </action>
  <action>Implement user's feedback and iterate</action>
  <action>Show updated content and check satisfaction</action>
</check>

<check if="option 3 - proceed">
  <action>Confirm user is satisfied and ready for output generation</action>
  <action>Proceed to final output</action>
  <goto step="15">Generate final output</goto>
</check>

<ask>Are you satisfied with the content now, or shall we continue refining? [satisfied/continue-refining]</ask>

<check if="satisfied">
  <break>Exit refinement loop</break>
</check>

<check if="continue-refining">
  <continue>Repeat refinement</continue>
</check>
</step>

<step n="15" goal="Generate final outputs and optional Medium publishing">
<action>Generate the final blog post outputs</action>

<action>Create the markdown file:

**File Structure:**
```markdown
---
title: {{blog_title}}
author: {{user_name}}
date: {{date}}
tags: [{{blog_tags}}]
description: {{seo_description}}
---

[Complete blog content with all sections, code, visuals]
```

**Include:**
- Frontmatter with metadata
- Complete blog content
- All code examples
- Mermaid diagrams
- Image references
- Tables
- References/links section

Save to: {output_folder}/blog-{{topic_slug}}-{{date}}.md
</action>

<action>If implementation code was created:
- Ensure code folder exists at: {output_folder}/blog-code-{{topic_slug}}/
- Include README with setup instructions
- Reference code folder in blog post
</action>

<action>Create a blog assets summary:
- List all screenshots/images needed
- List all external resources linked
- Note any dependencies for publication
</action>

<template-output>blog_title</template-output>
<template-output>blog_tags</template-output>
<template-output>seo_description</template-output>
<template-output>final_blog_content</template-output>
<template-output>output_file_path</template-output>
</step>

<step n="16" goal="Optional Medium publishing automation">
<ask>Would you like to automatically publish this to Medium as a draft using chrome-devtools MCP? [yes/no]</ask>

<check if="yes">
  <action>Prepare Medium publishing automation:

**Pre-Publishing:**
1. Ask user for Medium draft page URL (or instruct how to open new draft)
2. Analyze blog content for Medium-specific formatting needs
3. Prepare content sections for sequential pasting

**Medium Formatting Strategy:**
- Break content into logical sections
- Identify code blocks (Medium has special code block UI)
- Note image insertion points
- Track heading levels for proper formatting
  </action>

  <action>Execute chrome-devtools MCP automation:

**Step-by-Step Automation:**

1. **Navigate to Medium draft page**
   - Open provided URL or new draft

2. **Paste and format title**
   - Click title field
   - Paste blog title
   - Verify formatting

3. **Paste and format content sections**
   For each content section:
   - Click in editor
   - Paste section text
   - Apply proper formatting:
     - Headers (click and select H2, H3 as needed)
     - Bold/italic (apply to keywords)
     - Links (highlight text, click link button, paste URL)

4. **Insert code blocks**
   For each code example:
   - Click where code should go
   - Click code block button (or use keyboard shortcut)
   - Paste code
   - Verify syntax highlighting

5. **Insert images**
   For each image reference:
   - Click image insertion point
   - Upload image (if automated upload supported)
   - Or note manual step needed
   - Add image caption

6. **Add tags**
   - Click tags section
   - Add relevant tags from blog_tags

7. **Save as draft**
   - Click save/publish button
   - Select "Save as draft" option
   - Confirm save

**Error Handling:**
- If any step fails, pause and report to user
- Provide manual instructions as fallback
- Verify each major step before proceeding
  </action>

  <action>Report results to user:
  - "Medium draft created successfully!"
  - Provide draft URL if available
  - Note any manual steps remaining:
    - Images to upload
    - Final formatting checks
    - Preview before publishing
  </action>

  <template-output>medium_draft_url</template-output>
</check>

<check if="no">
  <action>Provide manual Medium publishing tips:

**To publish to Medium manually:**

1. Copy the markdown content
2. Open Medium and create new story
3. Paste content (Medium will auto-convert some markdown)
4. Format manually:
   - Apply heading styles
   - Insert code blocks
   - Upload images
   - Add links
5. Add tags and SEO description
6. Save as draft or publish

The markdown file is ready at: {{output_file_path}}
  </action>
</check>
</step>

<step n="17" goal="Workflow completion and summary">
<action>Provide comprehensive completion summary to {user_name}:

**📝 Technical Blog Post Created!**

**Outputs:**
- Blog post: {{output_file_path}}
- Code demo: {output_folder}/blog-code-{{topic_slug}}/ (if applicable)
- Visual assets: [list locations]

**Content Summary:**
- Title: {{blog_title}}
- Type: {{content_type}}
- Target audience: {{target_audience}}
- Word count: [estimate]
- Code examples: [count]
- Diagrams: [count]
- Tables: [count]

**Quality Checks Passed:**
✅ Technical accuracy verified
✅ All sections complete
✅ Human-quality writing (no AI slop)
✅ Visual aids integrated
✅ Ready for publication

**Next Steps:**
1. Review the final content in: {{output_file_path}}
2. Test code examples one more time (if applicable)
3. Publish to your preferred platform:
   - Dev.to: Copy markdown directly
   - Personal blog: Use markdown file
   - Medium: [Already drafted / Follow manual steps]
4. Share with your audience!

**Publishing Platforms:**
- ✅ Markdown format works on: Dev.to, GitHub, personal blogs
- ✅ Medium: [Draft created / Ready for manual posting]

Great work on creating this comprehensive technical content! 🚀
</action>

<action>Ask if there's anything else needed:
- Additional formats needed?
- Want to create a social media summary?
- Need help with anything else?
</action>
</step>

</workflow>
