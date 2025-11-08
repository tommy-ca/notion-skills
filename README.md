# Notion Skills - Claude Plugins Marketplace

A comprehensive marketplace of Claude skills for productive Notion workflows. Transform how you work with Notion by leveraging AI-powered assistance for knowledge capture, meeting intelligence, research documentation, and specification implementation.

## Overview

Notion Skills provides four specialized, autonomous Claude skills that integrate seamlessly with Notion:

- **Knowledge Capture** - Transform conversations and discussions into structured Notion documentation
- **Meeting Intelligence** - Prepare for meetings with comprehensive context, agendas, and background materials
- **Research Documentation** - Conduct research and document findings with proper sourcing and organization
- **Spec-to-Implementation** - Convert specifications into detailed implementation plans with task tracking

These skills automatically activate when relevant to your task, enhancing productivity without requiring explicit invocation.

## Project Structure

```
notion-skills/
├── .claude-plugin/
│   ├── marketplace.json              # Marketplace registry
│   └── plugin.json                   # Root plugin metadata (deprecated)
├── .gitignore
├── CLAUDE.md                         # Claude Code integration guide
├── README.md                         # This file
├── plugins/
│   └── notion-skills/
│       ├── .claude-plugin/
│       │   └── plugin.json           # Notion Skills plugin metadata
│       ├── skills/
│       │   ├── knowledge-capture/
│       │   │   ├── SKILL.md          # Skill definition
│       │   │   ├── reference/        # Templates and guides
│       │   │   ├── evaluations/      # Test scenarios
│       │   │   └── examples/         # Usage examples
│       │   ├── meeting-intelligence/
│       │   ├── research-documentation/
│       │   └── spec-to-implementation/
│       ├── agents/                   # (Optional) Custom agent definitions
│       ├── commands/                 # (Optional) Slash commands
│       ├── CLAUDE.md                 # Plugin-specific integration guide
│       └── README.md                 # Plugin-specific documentation
├── LICENSE
└── CONTRIBUTING.md
```

## Installation

### Via Claude Code Plugin System

```bash
# Clone the repository to your Claude plugins directory
git clone https://github.com/tommy-ca/notion-skills.git \
  ~/.claude/plugins/notion-skills

# Restart Claude Code
# Skills will automatically load and become available
```

### Manual Setup

1. Copy the `notion-skills` directory into `~/.claude/plugins/`
2. Restart Claude Code
3. Configure Notion API token (see Configuration section)

## Configuration

### 1. Get Notion API Token

1. Visit [Notion Developer Portal](https://www.notion.so/my-integrations)
2. Click "Create new integration"
3. Fill in integration details
4. Copy your API token

### 2. Share Notion Databases

For each database you want the skills to access:

1. Open the database in Notion
2. Click "Share" button
3. Select your integration
4. Grant "Edit" permissions

### 3. Set Environment Variable

```bash
export NOTION_API_TOKEN=your_token_here
```

Or configure in Claude Code settings for persistent storage.

## Available Skills

### 1. Knowledge Capture

Transform conversations into structured documentation.

**Activates when you:**
- Ask to organize meeting notes
- Want to document a discussion
- Need to extract decisions and action items
- Wish to create knowledge base articles

**Example:**
```
"Document this discussion in Notion with decisions and action items"
→ Knowledge Capture activates
→ Creates meeting summary with clear structure
```

**Outputs:**
- Meeting summaries with action items
- Decision records with rationale
- FAQ documents from discussions
- Learning documents from experiences
- Process documentation

**More Info:** See `plugins/notion-skills/skills/knowledge-capture/`

---

### 2. Meeting Intelligence

Prepare for productive meetings with comprehensive context.

**Activates when you:**
- Ask to prepare for an upcoming meeting
- Want to gather context on a topic
- Request a comprehensive meeting agenda
- Need background materials for participants

**Example:**
```
"Help me prepare for my 2pm meeting with the product team"
→ Meeting Intelligence activates
→ Gathers relevant context, creates agenda
```

**Outputs:**
- Meeting agendas with timing
- Background context gathered from Notion
- Pre-read materials
- Discussion talking points
- Risk/blocker identification

**More Info:** See `plugins/notion-skills/skills/meeting-intelligence/`

---

### 3. Research Documentation

Document research findings with proper sourcing.

**Activates when you:**
- Ask to research a specific topic
- Want to document research findings
- Request competitive or market analysis
- Need to create a literature review

**Example:**
```
"Research React vs Vue frameworks and document findings in Notion"
→ Research Documentation activates
→ Conducts research, creates sourced summary
```

**Outputs:**
- Quick briefs with key findings
- Comparison matrices
- Research summaries
- Comprehensive reports
- Decision memos

**More Info:** See `plugins/notion-skills/skills/research-documentation/`

---

### 4. Spec-to-Implementation

Convert specifications into detailed implementation plans.

**Activates when you:**
- Ask to create an implementation plan
- Want to break down feature specifications
- Need a project timeline with estimates
- Request actionable task lists from requirements

**Example:**
```
"Create an implementation plan for this API specification"
→ Spec-to-Implementation activates
→ Generates detailed task breakdown with timeline
```

**Outputs:**
- Implementation plans with phases
- Task breakdowns by component
- Effort estimates and timeline
- Dependency maps
- Progress tracking structure

**More Info:** See `plugins/notion-skills/skills/spec-to-implementation/`

## How Skills Work

### Model-Invoked Activation

Claude skills are **model-invoked**, meaning Claude automatically decides when to activate a skill based on:

1. **Your request** - Is this task related to the skill's purpose?
2. **Skill description** - Does the skill match what you're asking?
3. **Context** - Is this the right tool for this situation?

**You don't need to explicitly call skills** - they activate automatically when appropriate.

### Token Efficiency

Skills are designed to be token-efficient:

- **Initial cost**: Minimal tokens for skill metadata
- **On demand**: Full documentation loads only when skill is used
- **Smart activation**: Only relevant skills consume tokens
- **Result**: Lean, focused context for your requests

## Development & Contributing

### Project Standards

- Each skill is contained in its own directory under `plugins/notion-skills/skills/`
- Skill definitions (`SKILL.md`) are under 500 lines
- Detailed documentation lives in `reference/` subdirectories
- Test scenarios included in `evaluations/` subdirectories
- Usage examples provided in `examples/` subdirectories

### Adding a New Skill

1. Create a directory: `plugins/notion-skills/skills/your-skill-name/`
2. Add `SKILL.md` with YAML frontmatter:
   ```markdown
   ---
   name: your-skill-name
   description: Brief description of the skill
   ---
   ```
3. Create supporting directories:
   - `reference/` - Documentation and templates
   - `evaluations/` - Test scenarios
   - `examples/` - Usage examples
4. Update this README with the new skill information
5. Submit a pull request

### Skill Structure Template

```
your-skill-name/
├── SKILL.md                    # Main skill definition
├── reference/
│   ├── guide-1.md
│   └── guide-2.md
├── evaluations/
│   ├── README.md
│   └── scenario-1.json
└── examples/
    └── example-1.md
```

### Testing Skills

Each skill includes evaluation scenarios in the `evaluations/` directory. To test a skill:

1. Review the evaluation scenarios
2. Use Claude Code to activate the skill
3. Run through test cases
4. Validate against success criteria
5. Document any issues

## Documentation Structure

- **README.md** - This file; overview and installation
- **CLAUDE.md** - Claude Code integration details
- **plugins/notion-skills/skills/{skill-name}/SKILL.md** - Individual skill documentation
- **plugins/notion-skills/skills/{skill-name}/reference/** - Templates and guides
- **plugins/notion-skills/skills/{skill-name}/evaluations/** - Test scenarios
- **plugins/notion-skills/skills/{skill-name}/examples/** - Usage examples

## Architecture Decisions

### Marketplace Pattern

We follow the [Every Marketplace](https://github.com/EveryInc/every-marketplace) pattern:

- **Marketplace registry** (`marketplace.json`) for plugin discovery
- **Plugin-level organization** under `plugins/notion-skills/`
- **Skill grouping** within a single plugin
- **Scalable structure** allowing future additional plugins

### Skill Definition Pattern

We follow the [Notion Cookbook](https://github.com/makenotion/notion-cookbook) pattern:

- **Concise SKILL.md** (< 500 lines) for core definition
- **Modular reference/** for detailed guidance
- **Evaluation scenarios** for consistent testing
- **Practical examples** for user education

## Troubleshooting

### Skill Not Activating

**Check:**
- Skill description matches your request
- Claude Code is updated to latest version
- Restart Claude Code to reload skills
- Notion API token is configured

**Solution:**
- Be more specific in your request
- Include keywords from skill description
- Check integration is working with test call

### Notion API Errors

**Check:**
- API token is valid
- Target database is shared with integration
- Integration has "Edit" permissions
- Database IDs are correct

**Debug:**
- Test token with curl: `curl -H "Authorization: Bearer $TOKEN" https://api.notion.com/v1/users/me`
- Verify database access in Notion UI
- Check integration settings in Developer Console

### Performance Issues

**Optimize:**
- Limit database scope (not querying entire workspace)
- Use targeted search queries
- Increase timeout values for large operations
- Consider breaking large operations into steps

## Resources

- [Official Claude Skills Documentation](https://code.claude.com/docs/en/skills)
- [Claude Plugins Reference](https://code.claude.com/docs/en/plugins)
- [Notion API Documentation](https://developers.notion.com)
- [Notion Cookbook](https://github.com/makenotion/notion-cookbook)
- [Every Marketplace](https://github.com/EveryInc/every-marketplace)

## Support

For issues, questions, or feedback:

- **GitHub Issues** - Report bugs or request features
- **Documentation** - Check CLAUDE.md for integration details
- **Skill-Specific Help** - See individual skill directories
- **Notion API Help** - Consult Notion developer documentation

## License

MIT License - See LICENSE file for details

## Contributing

Contributions are welcome! Please see CONTRIBUTING.md for guidelines.

---

**Ready to enhance your Notion workflows?** Install Notion Skills and let Claude help you capture knowledge, prepare for meetings, conduct research, and implement specifications more effectively.

For detailed integration instructions, see [CLAUDE.md](./CLAUDE.md).
