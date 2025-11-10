# Technical Blog Creator Workflow

Create comprehensive, high-quality technical blog posts with working code demonstrations, detailed visual aids, and human-readable content optimized for AI Engineers, MLEs, Software Engineers, and AI Researchers.

## Purpose

Transform technical topics into publication-ready blog content that stands out from generic AI-generated posts. This workflow guides you through planning, research, implementation, content creation, and quality validation to produce blog posts that provide real value to technical audiences.

## Content Types Supported

- **Academic Paper Summaries**: Distill complex research papers into accessible summaries
- **Step-by-Step Tutorials**: Create comprehensive how-to guides with working code
- **New Feature Highlights**: Showcase and explain new library/framework features
- **Technical Demos**: Build and document proof-of-concept implementations

## Key Features

### 📋 Comprehensive Planning
- Detailed content plan with section and subsection breakdown
- Implementation plan for code demonstrations
- Visual content strategy (diagrams, screenshots, tables)

### 🔍 Deep Research Integration
- Generates deep research prompts for external services (Perplexity, Claude with web search)
- Integrates MCP services:
  - **deepwiki**: Public repository wikis and documentation
  - **context7**: Library documentation and API references
  - **chrome-devtools**: Browser automation for demos and Medium publishing

### 💻 Full Code Implementation
- Creates complete, runnable codebases
- Supports multiple languages (Python, JavaScript/TypeScript, Go, Rust)
- Includes dependencies, configuration, and setup instructions
- User testing phase with artifact collection

### 🎨 Rich Visual Content
- Mermaid/PlantUML diagram generation
- Automated screenshot capture via chrome-devtools MCP
- Markdown table generation
- Image integration and captioning

### ✅ Rigorous Quality Validation
- **AI Slop Detection**: Ensures human-quality writing (not generic AI-generated text)
- Technical accuracy verification
- Content completeness checks
- Readability and flow assessment
- Iterative refinement loop

### 🚀 Multi-Platform Publishing
- Platform-agnostic markdown output
- Works on Dev.to, personal blogs, GitHub
- **Automated Medium publishing** via chrome-devtools MCP
- SEO metadata generation

## Workflow Phases

### Phase 1: Planning & Structure
1. Gather topic, content type, and initial references
2. Create detailed content plan
3. Generate implementation plan (if code demo needed)

### Phase 2: Research & Knowledge Gathering
4. Generate comprehensive deep research prompt
5. User runs external research
6. Query MCP services for technical documentation
7. Organize and synthesize all findings

### Phase 3: Implementation (Optional)
8. Create complete codebase structure
9. User tests implementation and collects artifacts
10. Generate/collect visual aids

### Phase 4: Content Creation
11. Draft complete blog content with all gathered context
12. Generate and integrate visual elements (diagrams, tables, screenshots)

### Phase 5: Quality Validation & Publishing
13. Self-reflection and comprehensive quality validation
14. Iterative refinement based on feedback
15. Generate final markdown output
16. Optional automated Medium publishing
17. Completion summary and next steps

## Prerequisites

### Required MCP Servers

1. **deepwiki MCP**: For accessing public repository wikis
2. **context7 MCP**: For library documentation and API references
3. **chrome-devtools MCP**: For browser automation and Medium publishing

### Optional Tools

- Deep research service (Perplexity, Claude with web search, or custom tool)
- Code testing environment for chosen language
- Medium account (for automated publishing)

## Usage

### Invocation

```bash
# Via BMAD command
workflow technical-blog-creator

# Or via slash command
/bmad:bmm:workflows:technical-blog-creator
```

### Input Requirements

At workflow start, you'll need:
- **Topic**: The technical subject you want to write about
- **Content Type**: Academic summary, tutorial, feature highlight, or demo
- **Target Audience**: Who will read this (AI Engineers, MLEs, SWEs, researchers)
- **Technical Level**: Beginner, Intermediate, or Advanced
- **Initial References**: Any starting materials (URLs, docs, papers, repos)

### Optional Inputs

- Existing code to reference or build upon
- Specific libraries/frameworks to cover
- Research questions you want answered

## Outputs

### Primary Output

**Markdown Blog Post**: `{output_folder}/blog-{topic-slug}-{date}.md`

Includes:
- Frontmatter with metadata (title, author, date, tags, SEO description)
- Complete blog content with all sections
- Integrated code examples
- Mermaid diagrams
- Image references
- Tables
- References and resources section

### Secondary Outputs (if applicable)

**Code Repository**: `{output_folder}/blog-code-{topic-slug}/`

Contains:
- Complete project structure
- All source code files
- Dependency files (requirements.txt, package.json, etc.)
- Configuration files
- README with setup instructions

**Medium Draft** (optional): Automated draft creation on Medium platform

## Quality Standards

### Human-Quality Writing

This workflow enforces strict quality standards to ensure content reads naturally and provides real value:

**✅ Required:**
- Specific, concrete details and examples
- Personal insights and technical opinions
- Authentic, conversational voice
- Deep technical explanations with nuance
- Natural sentence variety
- Evidence-backed claims

**❌ Prohibited (AI Slop):**
- Generic openings ("In today's fast-paced world...")
- Overused transitions in every paragraph
- Vague statements without examples
- Formulaic sentence patterns
- Buzzwords without substance
- Surface-level explanations

### Technical Accuracy

- All code examples are runnable and tested
- Library/API references verified via MCP services
- Technical claims backed by documentation or research
- Best practices demonstrated

### Visual Excellence

- Clear, informative diagrams
- Relevant screenshots with captions
- Well-formatted tables
- Sufficient visual variety

## Example Use Cases

### 1. Tutorial: Building a RAG Application

**Input:**
- Topic: "Building a Production-Ready RAG System with LangChain and Pinecone"
- Content Type: Step-by-step tutorial
- Audience: AI Engineers (Intermediate)

**Output:**
- Complete blog post with introduction, setup, implementation, testing, deployment
- Full Python codebase with LangChain integration
- Architecture diagrams (Mermaid)
- Screenshots of vector database setup
- Code examples with explanations
- Testing artifacts

### 2. Paper Summary: Latest LLM Research

**Input:**
- Topic: "Understanding Chain-of-Thought Prompting: A Summary of Recent Research"
- Content Type: Academic paper summary
- Audience: AI Researchers (Advanced)

**Output:**
- Blog post breaking down key findings
- Comparison tables of different approaches
- Example prompts and results
- Links to original papers
- Implications for practitioners

### 3. Feature Highlight: New Library Release

**Input:**
- Topic: "What's New in FastAPI 0.110: Async Dependency Injection"
- Content Type: Feature highlight
- Audience: Software Engineers (Intermediate)

**Output:**
- Blog post explaining new features
- Code examples comparing old vs new approaches
- Migration guide
- Performance benchmarks (tables)
- Screenshots of development workflow

## Tips for Best Results

### Planning Phase
- Provide detailed initial references for better research
- Be specific about what aspects of the topic interest you
- Clarify target audience's assumed knowledge level

### Research Phase
- Take time with the deep research prompt - it's foundational
- Review MCP documentation findings and suggest additional queries if needed
- Don't skip the research synthesis step

### Implementation Phase
- Test the generated code thoroughly
- Collect diverse artifacts (success cases, edge cases, errors)
- Take screenshots during testing for authentic visuals

### Content Creation Phase
- Review drafts critically for AI slop indicators
- Provide specific feedback on sections that need work
- Don't hesitate to request rewrites of generic-sounding content

### Publishing Phase
- Review the quality assessment carefully
- Use the refinement loop to achieve publication quality
- Test automated Medium publishing in draft mode first

## Workflow Customization

### Skipping Implementation

If your blog post doesn't need code demonstrations:
- Answer "no" when asked if implementation is needed (Step 3)
- Workflow skips steps 8-10 and proceeds directly to content creation

### Manual vs Automated Screenshots

- **Manual**: User provides screenshots during testing (Step 9)
- **Automated**: Use chrome-devtools MCP for browser automation (Step 10)
- **Hybrid**: Combine both approaches as needed

### Medium Publishing Options

- **Automated**: Workflow uses chrome-devtools MCP to create formatted draft
- **Manual**: Workflow provides instructions for manual publishing
- **Skip**: Just generate markdown for other platforms

## Troubleshooting

### Research Findings Insufficient

**Solution:** In Step 6-7, request additional MCP queries or manual research for specific gaps identified

### Code Doesn't Work

**Solution:** Step 9 includes debugging loop - provide error messages and workflow will fix issues

### Content Feels Generic (AI Slop)

**Solution:** Step 13-14 include AI slop detection and refinement loop - request specific rewrites of flagged sections

### Visual Aids Missing

**Solution:** Reference the content plan (Step 2) and ensure all visual placeholders are addressed in Step 12

### Medium Automation Fails

**Solution:** Workflow provides manual publishing instructions as fallback

## Integration with Other BMAD Workflows

### Complementary Workflows

- **brainstorming**: Use before this workflow to explore blog topic ideas
- **research**: For deeper market/competitive analysis
- **document-project**: When writing about an existing codebase

### Workflow Outputs as Inputs

- Research reports can be reused for multiple related blog posts
- Code implementations can be referenced in future tutorials
- Content plans can be templates for series of posts

## Version History

- **v1.0**: Initial release with full feature set
  - 5 phases, 17 steps
  - MCP integration (deepwiki, context7, chrome-devtools)
  - AI slop detection and quality validation
  - Automated Medium publishing
  - Multi-language code generation

## Contributing

To improve this workflow:
1. Test with various technical topics
2. Provide feedback on quality validation criteria
3. Suggest additional MCP integrations
4. Report issues or edge cases
5. Share successful blog posts created with this workflow

## License

Part of the BMAD Method Module - BMad Framework

---

**Created:** 2025-11-10
**Author:** BMad
**Module:** bmm (BMad Method)
**Type:** Document Workflow with Action & Interactive elements
