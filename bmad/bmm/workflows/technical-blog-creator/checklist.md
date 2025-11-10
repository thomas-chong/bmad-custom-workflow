# Technical Blog Post Validation Checklist

## 1. Content Planning and Structure

- [ ] Content plan created with clear sections and subsections
- [ ] All planned sections are present in final blog
- [ ] Logical flow from introduction through main content to conclusion
- [ ] Appropriate depth for target audience ({{target_audience}})
- [ ] Content type requirements met ({{content_type}})

## 2. Technical Accuracy

- [ ] All code examples are syntactically correct and runnable
- [ ] Code examples match the implementation (if applicable)
- [ ] Technical claims are accurate and verifiable
- [ ] Library/API references are current and correct (verified via context7/deepwiki MCP)
- [ ] No outdated information or deprecated APIs referenced
- [ ] Error handling demonstrated where appropriate
- [ ] Best practices followed in code examples

## 3. Research Integration

- [ ] Deep research findings integrated throughout content
- [ ] MCP documentation (deepwiki, context7) referenced appropriately
- [ ] All research questions from prompt addressed
- [ ] Citations and references included for key claims
- [ ] External resources linked where relevant

## 4. Implementation Quality (if applicable)

- [ ] Complete codebase structure created
- [ ] All dependencies listed (requirements.txt, package.json, etc.)
- [ ] Setup instructions clear and complete
- [ ] Code tested and verified working by user
- [ ] Comments explain key concepts
- [ ] Modular and maintainable code structure
- [ ] Appropriate for target technical level

## 5. Visual Content Quality

- [ ] All planned diagrams generated using Mermaid/PlantUML
- [ ] Diagrams are clear, labeled, and informative
- [ ] Screenshots captured at appropriate points
- [ ] Screenshots have descriptive captions
- [ ] Tables properly formatted in markdown
- [ ] Images referenced correctly in markdown (`![alt](path)`)
- [ ] Visual aids enhance understanding (not just decorative)
- [ ] Sufficient visual variety (diagrams, screenshots, tables)

## 6. Content Completeness

- [ ] Introduction has engaging hook
- [ ] Problem statement or motivation clearly stated
- [ ] All content plan sections addressed
- [ ] Code examples have sufficient context and explanation
- [ ] Conclusion summarizes key takeaways (3-5 points)
- [ ] Next steps or further reading suggested
- [ ] References and resources section included
- [ ] No placeholder text remaining (`[TODO]`, `[INSERT]`, etc.)

## 7. Readability and Flow

- [ ] Logical section progression
- [ ] Clear transitions between topics
- [ ] Consistent terminology throughout
- [ ] Appropriate technical depth maintained
- [ ] Sentence length varies (not repetitive patterns)
- [ ] Paragraphs focused and cohesive (one main idea per paragraph)
- [ ] Headers properly structured (H1 → H2 → H3 hierarchy)
- [ ] Code blocks have language tags for syntax highlighting

## 8. AI Slop Detection (CRITICAL)

### ❌ Must NOT Contain:

- [ ] Generic openings ("In today's fast-paced world...", "In the ever-evolving landscape of...")
- [ ] Overused transitions appearing repeatedly ("Moreover", "Furthermore", "Additionally" in every paragraph)
- [ ] Vague statements without concrete examples or evidence
- [ ] Formulaic sentence patterns (same structure repeated)
- [ ] Buzzwords without substance or explanation
- [ ] Surface-level explanations lacking depth
- [ ] Repetitive phrasing or word choice
- [ ] Corporate-speak or marketing jargon without purpose

### ✅ Must Contain:

- [ ] Specific, concrete details and examples
- [ ] Personal insights, opinions, or perspectives
- [ ] Authentic, conversational human voice
- [ ] Technical depth with nuanced explanations
- [ ] Natural sentence variety
- [ ] Practical, actionable information
- [ ] Evidence-backed claims (code, research, documentation)
- [ ] Engaging narrative that holds reader interest

## 9. Writing Quality

- [ ] Direct and conversational tone
- [ ] Technical but accessible language
- [ ] Active voice preferred over passive
- [ ] Clear explanations without unnecessary jargon
- [ ] Examples illustrate concepts effectively
- [ ] Writing maintains reader engagement
- [ ] No grammatical or spelling errors
- [ ] Consistent style and formatting

## 10. SEO and Metadata

- [ ] SEO-friendly title (clear, descriptive, keyword-rich)
- [ ] Meta description created (150-160 characters)
- [ ] Relevant tags identified (5-10 tags)
- [ ] Frontmatter complete with all metadata
- [ ] Title accurately reflects content
- [ ] Description entices readers while being accurate

## 11. Platform Compatibility

- [ ] Markdown syntax correct and standard
- [ ] Code blocks formatted with language tags
- [ ] Images use relative paths or proper URLs
- [ ] Tables formatted correctly in markdown
- [ ] Frontmatter compatible with target platforms
- [ ] Content works on multiple platforms (Dev.to, personal blog, Medium)

## 12. Medium Publishing (if applicable)

- [ ] Medium draft created via chrome-devtools MCP automation
- [ ] Title pasted and formatted correctly
- [ ] Content sections pasted and formatted
- [ ] Headers applied (H2, H3 levels)
- [ ] Code blocks inserted with proper formatting
- [ ] Images uploaded and positioned correctly
- [ ] Links added and verified
- [ ] Tags added to draft
- [ ] Draft saved successfully
- [ ] OR manual publishing instructions provided

## 13. Final Quality Checks

- [ ] Overall content provides real value to readers
- [ ] Readers can take action based on content
- [ ] Content stands out from generic posts on same topic
- [ ] Technical accuracy verified end-to-end
- [ ] Writing quality matches human-written content
- [ ] Visual aids sufficient and well-integrated
- [ ] All promised content from introduction delivered
- [ ] Call-to-action or next steps clear

## 14. Delivery and Documentation

- [ ] Blog post saved to correct location: `{output_folder}/blog-{{topic_slug}}-{{date}}.md`
- [ ] Code implementation saved to: `{output_folder}/blog-code-{{topic_slug}}/` (if applicable)
- [ ] All assets organized and referenced correctly
- [ ] README created for code repository (if applicable)
- [ ] Completion summary provided to user
- [ ] Next steps for publication documented

---

## Issue Tracking

### Critical Issues (Must Fix Before Publishing)

None identified / [List any critical issues found]

### Important Improvements (Should Fix)

None identified / [List important improvements needed]

### Optional Enhancements (Could Fix)

None identified / [List nice-to-have improvements]

---

## Quality Assessment Result

**Overall Status:** ☐ Ready to Publish | ☐ Minor Refinement Needed | ☐ Major Revision Required

**Reviewer Notes:**

[Space for quality assessment notes from Step 13 of workflow]

---

**Validation Completed:** {{date}}
**Validated By:** AI Workflow Engine
**User Approval:** ☐ Approved | ☐ Needs Revision
