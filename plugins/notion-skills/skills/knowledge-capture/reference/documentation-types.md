# Knowledge Capture - Documentation Types Guide

This guide explains the different documentation types that Knowledge Capture can create and when to use each one.

## Documentation Types

### 1. How-To Guides

**Purpose:** Step-by-step instructions for accomplishing a specific task

**Structure:**
- Title (action-oriented, e.g., "How to Set Up OAuth")
- Overview (what this guide covers and why it matters)
- Prerequisites (knowledge, tools, or access needed)
- Numbered Steps (clear, sequential instructions)
- Troubleshooting (common issues and solutions)
- Related Resources (links to other documentation)

**Example Context:**
```
Conversation about: Implementing authentication flow
→ Knowledge Capture suggests: How-To Guide
→ Output: "How to Implement OAuth 2.0 in Node.js"
```

**Best Practices:**
- Keep steps atomic (one action per step)
- Include expected outputs/confirmations
- Add screenshots or examples when possible
- Test instructions before publishing

---

### 2. Decision Records

**Purpose:** Document important decisions and their rationale

**Structure:**
- Title (clear decision statement)
- Date & Context (when and why this decision was needed)
- Problem Statement (what needed to be decided)
- Options Considered (alternatives with pros/cons)
- Decision (what was decided and why)
- Consequences (impacts and follow-ups)
- Related Decisions (decisions that connect to this one)

**Example Context:**
```
Conversation about: Choosing between microservices and monolith
→ Knowledge Capture suggests: Decision Record
→ Output: "Architecture Decision: Monolithic vs. Microservices"
```

**Best Practices:**
- Make decisions explicit and documented
- Include options you rejected and why
- Document impacts as they become clear
- Revisit periodically to validate decisions

---

### 3. FAQ Documents

**Purpose:** Provide quick answers to commonly asked questions

**Structure:**
- Topic Title (the subject area)
- Questions (organized by category or importance)
- Answers (clear, concise, with examples)
- See Also (links to related topics)

**Example Context:**
```
Conversation about: Common questions about API usage
→ Knowledge Capture suggests: FAQ
→ Output: "API Integration FAQ"
```

**Best Practices:**
- Order by frequency and importance
- Keep answers concise but complete
- Include code examples where relevant
- Link to detailed documentation for deep dives

---

### 4. Meeting Summaries

**Purpose:** Capture outcomes from meetings

**Structure:**
- Meeting Details (date, attendees, purpose)
- Key Decisions (what was decided)
- Action Items (who, what, when)
- Discussion Summary (what was discussed)
- Next Steps (what happens next)
- Related Materials (linked documents)

**Example Context:**
```
Conversation from: Product planning meeting
→ Knowledge Capture suggests: Meeting Summary
→ Output: "Q4 Planning Meeting - November 9, 2025"
```

**Best Practices:**
- Capture decisions and action items immediately
- Make action items specific and assignable
- Link to relevant documentation
- Distribute summary within 24 hours

---

### 5. Learning Documents

**Purpose:** Preserve knowledge and learning from experiences

**Structure:**
- Situation (context and background)
- What Happened (the story or event)
- Key Learnings (takeaways and insights)
- Best Practices (applicable lessons)
- Resources (further reading)
- Related Learning (connected documents)

**Example Context:**
```
Conversation about: Why a deployment went wrong
→ Knowledge Capture suggests: Learning Document
→ Output: "Lessons from November Production Incident"
```

**Best Practices:**
- Focus on patterns and principles
- Be honest about mistakes
- Emphasize what you'd do differently
- Make it practical and actionable

---

### 6. Process Documentation

**Purpose:** Document standard processes and workflows

**Structure:**
- Process Name (clear, action-oriented)
- Purpose (why this process exists)
- Scope (when and where it applies)
- Responsibilities (who does what)
- Steps (detailed workflow)
- Approval (if needed)
- Review Schedule (how often to revisit)

**Example Context:**
```
Conversation about: How code reviews work in the team
→ Knowledge Capture suggests: Process Documentation
→ Output: "Code Review Process"
```

**Best Practices:**
- Keep current with team changes
- Include decision points and escalation paths
- Make roles and responsibilities clear
- Version and date your processes

---

## Selection Guidance

Use this flowchart to determine the best documentation type:

```
Question: What are you capturing?

├─ A task someone needs to do?
│  └─ How-To Guide
│
├─ A decision that was made?
│  └─ Decision Record
│
├─ Repeated questions?
│  └─ FAQ
│
├─ What happened in a meeting?
│  └─ Meeting Summary
│
├─ An experience to learn from?
│  └─ Learning Document
│
└─ A repeated workflow?
   └─ Process Documentation
```

---

## Linking Documentation

Once created, ensure new documentation is discoverable:

1. **Hub Pages**: Add to relevant index or category pages
2. **Backlinks**: Link from source materials
3. **Tags**: Use consistent tagging for search
4. **Cross-references**: Link to related documentation

## Best Practices Across All Types

- **Consistent Format**: Follow the structure for your doc type
- **Clear Titles**: Use descriptive, searchable titles
- **Dated/Versioned**: Include dates, especially for time-sensitive info
- **Author/Owner**: Know who to ask about updates
- **Regular Review**: Schedule periodic reviews to keep current
- **Examples**: Include concrete examples and templates
