# Claude Code Integration Guide

This document provides instructions for how Claude Code should interact with the Notion Skills plugin.

## Plugin Registration

This plugin provides four specialized skills that automatically activate when relevant:

```json
{
  "skills": [
    "knowledge-capture",
    "meeting-intelligence",
    "research-documentation",
    "spec-to-implementation"
  ]
}
```

## Skill Activation Triggers

### Knowledge Capture
Claude should activate this skill when the user:
- Asks to organize or document conversations
- Wants to convert meeting notes to structured documentation
- Requests to extract decisions or action items from discussions
- Needs to create knowledge base articles from discussions
- Asks to archive or preserve conversations

**Example triggers:**
- "Organize these meeting notes"
- "Document this discussion in Notion"
- "Extract action items from the meeting"
- "Turn this transcript into a knowledge base article"

### Meeting Intelligence
Claude should activate this skill when the user:
- Asks to prepare for an upcoming meeting
- Wants to gather context about a meeting topic
- Requests a comprehensive meeting agenda
- Needs background materials for a meeting
- Asks to review past interactions with meeting attendees

**Example triggers:**
- "Help me prepare for my meeting with..."
- "Create an agenda for tomorrow's meeting"
- "What do I need to know about..."
- "Gather context for this meeting"

### Research Documentation
Claude should activate this skill when the user:
- Asks to research a specific topic
- Wants to document research findings
- Requests a competitive analysis or market research
- Needs to create a literature review
- Asks to compare technologies or frameworks

**Example triggers:**
- "Research [topic] and document findings"
- "Create a competitive analysis for..."
- "Compare [option1] vs [option2]"
- "Build a knowledge base about..."

### Spec-to-Implementation
Claude should activate this skill when the user:
- Asks to convert a specification into an implementation plan
- Requests task breakdown for a feature or project
- Wants to create a project timeline with estimates
- Needs to generate a roadmap from requirements
- Asks to set up implementation tracking

**Example triggers:**
- "Create an implementation plan for..."
- "Break down this specification into tasks"
- "Generate a timeline for this feature"
- "Convert this spec into actionable tasks"

## Skill Usage Patterns

### Pattern 1: Direct Activation
```
User: "Help me prepare for my product strategy meeting"
↓
Claude analyzes request
↓
Activates Meeting Intelligence skill
↓
Gathers context, creates agenda
↓
Returns prepared meeting document
```

### Pattern 2: Chained Skills
```
User: "Research vector databases and document your findings"
↓
Claude activates Research Documentation skill
↓
Conducts research on vector databases
↓
If findings relevant to decisions: may activate Knowledge Capture
↓
Creates comprehensive research summary
```

### Pattern 3: Contextual Activation
```
User: "I have a new feature request. What do I do?"
↓
Claude analyzes request context
↓
Determines if spec is available
↓
If spec exists: may activate Spec-to-Implementation
↓
If meeting planned: may suggest Meeting Intelligence
↓
Provides appropriate guidance
```

## Integration Points

### Notion API Integration
All skills interact with Notion through:
- **API Token**: `NOTION_API_TOKEN` environment variable
- **Database IDs**: Specific to each skill's target databases
- **Data Format**: Notion blocks and page structure

### Environment Variables
Claude should check for these configuration variables:

```env
NOTION_API_TOKEN          # Required for all skills
NOTION_WORKSPACE_ID       # Optional: workspace identifier
```

### Error Handling
When Notion API errors occur, Claude should:
1. Inform the user of the specific error
2. Suggest configuration verification steps
3. Offer alternative approaches if available
4. Provide debugging information from API response

## Content Guidelines

### Documentation Quality Standards

Skills should produce documentation that:

- **Is Well-Structured**: Uses proper markdown hierarchy
- **Is Sourced**: Includes citations and source attribution
- **Is Actionable**: Contains clear next steps and assignments
- **Is Discoverable**: Includes keywords and cross-links
- **Is Maintainable**: Follows consistent formatting

### Notion Page Properties

When creating Notion pages, use these standard properties:

```
- Title: Clear, descriptive page title
- Created: Automatic timestamp
- Author: Claude or user (as appropriate)
- Status: Draft, In Progress, Complete, etc.
- Related: Links to related pages
- Tags: Categorization tags
- Last Updated: Automatic timestamp
```

## Skill-Specific Guidance

### Knowledge Capture
- Prioritize extracting decisions and action items
- Create clear ownership for action items
- Link to related documentation automatically
- Preserve original content while organizing it
- Include discussion context and context

### Meeting Intelligence
- Gather relevant background materials proactively
- Create detailed but scannable agendas
- Highlight potential discussion blockers
- Prepare data and examples in advance
- Include attendee context subtly

### Research Documentation
- Use consistent citation format throughout
- Organize findings hierarchically by topic
- Include methodology and search sources
- Create comparison matrices where appropriate
- Provide clear summaries of findings

### Spec-to-Implementation
- Break down requirements into atomic tasks
- Clearly identify dependencies
- Provide realistic effort estimates
- Use consistent task naming conventions
- Set up progress tracking structure

## Configuration Instructions

### For Users Installing the Plugin

1. **Get Notion API Token**
   ```
   Visit: https://www.notion.so/my-integrations
   Create new integration
   Copy API key
   ```

2. **Share Databases**
   - In Notion, open each target database
   - Click "Share" button
   - Select your integration
   - Choose "Edit" permission level

3. **Set Environment Variable**
   ```bash
   export NOTION_API_TOKEN=your_token_here
   ```

4. **Restart Claude Code**
   - Skills will load automatically
   - Test with: "Help me prepare for a meeting"

## Testing Skills

### Test Cases for Each Skill

**Knowledge Capture**
```
1. Provide meeting transcript
2. Request documentation in Notion
3. Verify: proper formatting, decision extraction, action items
```

**Meeting Intelligence**
```
1. Mention upcoming meeting
2. Request preparation assistance
3. Verify: agenda created, context gathered, relevant info compiled
```

**Research Documentation**
```
1. Request research on specific topic
2. Ask for Notion documentation
3. Verify: sources cited, findings organized, comparison included
```

**Spec-to-Implementation**
```
1. Provide project specification
2. Request implementation plan
3. Verify: tasks broken down, dependencies identified, timeline estimated
```

## Troubleshooting

### Skill Not Activating
- Verify request matches skill description
- Check Notion API token is set
- Ensure Claude Code is updated
- Restart Claude Code to reload skills

### Notion Errors
- Verify API token validity
- Check database is shared with integration
- Confirm database ID in configuration
- Review Notion API documentation

### Task Tracking Issues
- Verify database structure
- Check required fields exist
- Ensure write permissions set
- Validate database format

## Advanced Configuration

### Custom Notion Templates
Skills can use custom Notion templates for consistency:

```env
KNOWLEDGE_CAPTURE_TEMPLATE_ID=database_id
MEETING_INTELLIGENCE_TEMPLATE_ID=database_id
RESEARCH_DOCUMENTATION_TEMPLATE_ID=database_id
SPEC_TO_IMPLEMENTATION_TEMPLATE_ID=database_id
```

### Preference Settings
Users can customize behavior:

```env
CITATION_FORMAT=APA|MLA|Chicago|Harvard|IEEE
ESTIMATE_UNIT=hours|story_points|days|weeks
MEETING_AGENDA_STYLE=detailed|concise|executive
DOCUMENTATION_STYLE=technical|accessible|formal
```

## Version Compatibility

- **Claude Code**: v1.0.0+
- **Notion API**: v1.0
- **Skill System**: Claude Skills v1.0

## Support and Feedback

For issues or feedback:
- Check this guide first
- Review skill-specific documentation
- Check Notion API documentation
- Open an issue on GitHub

---

Last Updated: 2025-11-09
Plugin Version: 1.0.0
