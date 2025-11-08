# Notion Skills

A comprehensive collection of Claude skills for productive Notion workflows. These skills automatically activate when relevant to your task, helping you capture knowledge, prepare for meetings, conduct research, and implement specifications.

## Overview

Notion Skills enables Claude to intelligently assist with knowledge work through four specialized skills:

- **Knowledge Capture** - Transform conversations into structured Notion documentation
- **Meeting Intelligence** - Prepare for meetings with comprehensive context and agendas
- **Research Documentation** - Research topics and document findings with proper sourcing
- **Spec-to-Implementation** - Convert specifications into detailed implementation plans

## Quick Start

### Installation

1. **Via Claude Code Plugin System**
   ```bash
   # Clone this repository into your Claude plugins directory
   git clone https://github.com/yourusername/notion-skills.git ~/.claude/plugins/notion-skills
   ```

2. **Manual Installation**
   - Copy the `notion-skills` directory into `.claude/plugins/`
   - Restart Claude Code

### Setup

1. **Obtain Notion API Token**
   - Go to [Notion Developer Portal](https://www.notion.so/my-integrations)
   - Create a new integration
   - Copy your API token

2. **Configure Access**
   - Share relevant Notion databases with your integration
   - Store token securely in your environment or Notion settings

3. **Verify Installation**
   - Start Claude Code
   - Skills will automatically load and become available when relevant

## Available Skills

### 1. Knowledge Capture
**Captures conversations and discussions into structured documentation**

When to use:
- Converting meeting notes into organized documentation
- Archiving important conversations
- Extracting decisions and action items from discussions
- Building institutional knowledge bases

```
Request: "Organize these meeting notes into a Notion page"
→ Knowledge Capture skill activates
→ Creates structured documentation with decisions and action items
```

### 2. Meeting Intelligence
**Prepares you for productive meetings with comprehensive context**

When to use:
- Preparing for important meetings
- Gathering context about attendees and topics
- Creating comprehensive meeting agendas
- Reviewing past interactions with participants

```
Request: "Prepare me for my 2pm meeting with the product team"
→ Meeting Intelligence skill activates
→ Gathers relevant context and creates comprehensive agenda
```

### 3. Research Documentation
**Documents research findings with organized structure and proper sourcing**

When to use:
- Researching technologies or frameworks
- Conducting competitive analysis
- Building domain knowledge bases
- Creating literature reviews

```
Request: "Research React vs Vue frameworks and document findings"
→ Research Documentation skill activates
→ Creates well-sourced research summary
```

### 4. Spec-to-Implementation
**Converts specifications into detailed implementation plans**

When to use:
- Breaking down feature specifications into tasks
- Creating project implementation plans
- Generating task timelines and estimates
- Setting up progress tracking

```
Request: "Create an implementation plan for this API specification"
→ Spec-to-Implementation skill activates
→ Generates detailed task breakdown with timeline
```

## Architecture

```
notion-skills/
├── .claude-plugin/
│   └── plugin.json              # Plugin metadata
├── skills/
│   ├── knowledge-capture/
│   │   └── SKILL.md
│   ├── meeting-intelligence/
│   │   └── SKILL.md
│   ├── research-documentation/
│   │   └── SKILL.md
│   └── spec-to-implementation/
│       └── SKILL.md
├── README.md                     # This file
├── CLAUDE.md                     # Claude-specific instructions
└── .gitignore
```

## How Skills Work

Claude skills are **model-invoked** - Claude automatically decides when to use a skill based on:

1. **Task relevance** - Does the skill apply to what you're asking?
2. **Skill description** - Does the skill's purpose match your need?
3. **Context** - Is this the right tool for the current task?

You don't need to explicitly call skills; they activate automatically when appropriate.

### Token Efficiency

Skills are designed to be token-efficient:
- Skill metadata takes minimal tokens initially
- Full details load only when Claude determines the skill is needed
- Keeps your context lean and focused

## Requirements

- **Claude Code** - Latest version with skill support
- **Notion API Access** - Integration token with appropriate permissions
- **Notion Workspace** - Where documentation will be created/updated
- **Internet Connection** - For Notion API calls and external research

## Configuration

### Environment Variables

Set these in your Claude Code environment or Notion integration settings:

```env
NOTION_API_TOKEN=your_api_token_here
```

### Per-Skill Configuration

Each skill can be configured with specific settings:

**Knowledge Capture**
- Target database for captured knowledge
- Document template preference
- Metadata fields to capture

**Meeting Intelligence**
- Meeting database location
- Context database for background info
- Attendee information source

**Research Documentation**
- Research database location
- Citation format (APA, MLA, Chicago, etc.)
- Sources database for tracking references

**Spec-to-Implementation**
- Project database location
- Task tracking database
- Team member directory
- Estimation unit preference (hours, story points, etc.)

## Examples

### Example 1: Knowledge Capture

```
You: "Here's a transcript from our architecture meeting.
Can you organize it in Notion with the key decisions?"

Claude activates Knowledge Capture skill:
- Parses the meeting transcript
- Extracts key decisions and action items
- Creates organized Notion page with proper hierarchy
- Links related documentation
- Assigns action items with owners
```

### Example 2: Meeting Intelligence

```
You: "I have a meeting with the engineering team tomorrow about
our Q4 roadmap. Help me prepare."

Claude activates Meeting Intelligence skill:
- Searches for Q4 roadmap documentation
- Gathers recent engineering discussions and decisions
- Compiles team member information and expertise areas
- Creates comprehensive meeting agenda
- Identifies potential discussion points and blockers
```

### Example 3: Research Documentation

```
You: "I need to understand the current state of vector databases.
Research the top options and document everything in Notion."

Claude activates Research Documentation skill:
- Researches leading vector database options
- Compiles feature comparisons
- Documents use cases and trade-offs
- Creates sourced research summary with citations
- Organizes findings for easy reference
```

### Example 4: Spec-to-Implementation

```
You: "Convert this product specification into an implementation
plan with timeline and task assignments."

Claude activates Spec-to-Implementation skill:
- Parses specification and extracts requirements
- Breaks into user stories and tasks
- Identifies technical dependencies
- Estimates effort for each task
- Creates Notion implementation dashboard
- Assigns tasks and sets timeline
```

## Development

### Adding New Skills

To add a new skill to this collection:

1. Create a new directory in `skills/skill-name/`
2. Add `SKILL.md` with proper YAML frontmatter:
   ```markdown
   ---
   name: skill-name
   description: Brief description of what the skill does
   ---
   ```
3. Follow the structure of existing skills
4. Update this README with the new skill information
5. Test with Claude Code before deployment

### Extending Skills

Skills can be extended with:

- **Supporting documentation** - `reference.md`, `examples.md`, etc.
- **Scripts** - `scripts/` directory for utility functions
- **Templates** - `templates/` directory for document templates
- **Configuration files** - For complex setup requirements

## Troubleshooting

### Skill Not Activating

- Verify the skill description matches your request
- Check that Notion API token is configured
- Ensure you have the latest Claude Code version
- Restart Claude Code to reload skills

### Notion API Errors

- Verify your API token is valid
- Check that target databases are shared with the integration
- Ensure database IDs are correct
- Review Notion API error messages for specific issues

### Task Tracking Issues

- Verify database structure matches expected format
- Check that all required fields are present
- Ensure integration has write permissions

## Contributing

We welcome contributions! To contribute:

1. Fork this repository
2. Create a feature branch for your skill or improvement
3. Follow the existing skill structure and documentation style
4. Test thoroughly with Claude Code
5. Submit a pull request with detailed description

## Resources

- [Notion Skills Official Documentation](https://code.claude.com/docs/en/skills)
- [Claude Plugins Reference](https://code.claude.com/docs/en/plugins)
- [Notion API Documentation](https://developers.notion.com)
- [Notion Cookbook](https://github.com/makenotion/notion-cookbook)

## License

MIT License - See LICENSE file for details

## Support

For issues, questions, or feedback:
- Open an issue on GitHub
- Check existing documentation and FAQs
- Review Notion API documentation
- Consult Claude Code documentation

---

**Ready to supercharge your Notion workflows?** Install Notion Skills and let Claude help you capture knowledge, prepare for meetings, conduct research, and implement specifications more effectively.
