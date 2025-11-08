# Knowledge Capture - Best Practices

Guidelines for capturing knowledge effectively in Notion.

## Timing

**Capture Promptly**
- Document while context is fresh
- Aim to capture within 24 hours of the conversation
- Create placeholder if you'll document later

**Regular Maintenance**
- Review quarterly for accuracy
- Update links if pages move
- Archive outdated documentation
- Mark superseded content clearly

## Structure & Organization

**Clear Hierarchy**
- Use proper heading levels (H1, H2, H3, etc.)
- One main idea per section
- Logical flow from overview to details
- Include table of contents for long documents

**Consistent Templates**
- Use the same structure within document types
- Keep headers and sections predictable
- Use consistent formatting and styles

## Content Quality

**Be Specific**
- Use concrete examples over vague descriptions
- Include actual code, commands, or workflows
- Name specific tools and versions
- Be clear about what's required vs. optional

**Make It Actionable**
- Include clear next steps
- Provide decision criteria if applicable
- List prerequisites upfront
- Specify who needs to do what

**Prevent Orphaning**
- Link to hub pages or indexes
- Add to relevant category pages
- Use tags for discovery
- Include "Related Documents" section

## Linking & Discoverability

**Strategic Linking**
```
Example: How-To Guide on "Setting Up CI/CD"

Links to add:
- Source document (e.g., architecture decision)
- Related documents (deployment guide, monitoring)
- Hub page (DevOps/Infrastructure index)
- Team/person pages (who uses this)
```

**Tagging Strategy**
- Use consistent tag names across org
- Don't over-tag (3-5 tags per document)
- Use hierarchical tags: `process/deployment`, `tool/github`
- Example tags: `how-to`, `urgent`, `team-core`, `deprecated`

**Searchable Content**
- Use descriptive titles (not "Meeting Notes", use "Q4 Planning - Nov 9")
- Include keywords in description
- Put important terms in headings
- Use consistent terminology

## Collaborative Documentation

**Ownership & Updates**
- Designate an owner for each document
- Include last-updated date
- Make update process clear (who can edit)
- Document version/change history if needed

**Review Cycle**
- Schedule reviews for time-sensitive docs (quarterly for most)
- Mark review dates in document
- Create task reminders for reviews
- Document what changed and why

**Avoiding Duplication**
- Search before creating new docs
- Link to existing docs instead of copying
- Mark outdated docs clearly
- Consolidate when possible

## Different Formats

**Short Documents (< 5 screens)**
- Single Notion page
- No special structure needed
- Still add tags and links

**Medium Documents (5-20 screens)**
- Use databases for modular content
- Create table of contents
- Add navigation between sections

**Long Documents (> 20 screens)**
- Consider breaking into multiple pages
- Create parent pages with sub-pages
- Add clear navigation
- Link to each section from TOC

## Maintenance Patterns

**Quarterly Review Checklist**
- [ ] Is this still accurate?
- [ ] Are links still valid?
- [ ] Should we archive or consolidate?
- [ ] Are examples still relevant?
- [ ] Do we need to update tools/versions?

**Update Notification**
- When updating significant docs: notify stakeholders
- Add summary of what changed
- Update linked documents if needed
- Note the update in a changelog if important

## Common Pitfalls to Avoid

1. **Orphaned Documentation**: Always link to hub pages
2. **Outdated Examples**: Date-stamp time-sensitive information
3. **Vague Instructions**: Include specific steps and expected output
4. **No Context**: Explain why this documentation exists
5. **Over-Linking**: 3-5 key links is usually enough
6. **Inconsistent Format**: Follow templates for similar doc types
7. **Missing Ownership**: Know who maintains what
8. **Broken Links**: Periodically check and fix internal links

## Examples of Great Documentation

Look for these characteristics in well-documented knowledge:

✓ Clear purpose stated upfront
✓ Specific examples and code
✓ Step-by-step instructions when applicable
✓ Links to prerequisites and related docs
✓ Date or version information
✓ Clear ownership/maintainer
✓ Table of contents for long docs
✓ Searchable keywords in title and headings

## Tools & Templates

See the `templates/` directory for:
- How-To template
- Decision Record template
- FAQ template
- Meeting Summary template
- Learning Document template
- Process Documentation template
