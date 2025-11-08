# Spec to Implementation - Task Breakdown Guide

How to decompose specifications into well-structured, implementable tasks.

## Task Hierarchy

```
Specification Document
├── Requirement 1
│   ├── User Story 1.1
│   │   ├── Task 1.1.1 (Backend)
│   │   ├── Task 1.1.2 (Frontend)
│   │   └── Task 1.1.3 (Testing)
│   └── User Story 1.2
│       └── [Tasks...]
└── Requirement 2
    └── [User Stories and Tasks...]
```

## Task Properties

Each task should have:

| Property | Purpose | Example |
|----------|---------|---------|
| **Title** | Clear, action-oriented | "Implement user authentication endpoint" |
| **Description** | What, why, how | Details of implementation approach |
| **Acceptance Criteria** | How to know it's done | "Users can log in with email/password" |
| **Estimate** | Effort required | "5 story points" or "8 hours" |
| **Owner** | Who's doing it | "Alex Chen" |
| **Dependencies** | What must happen first | "Database schema finalized" |
| **Priority** | Urgency | "P0 - Blocking", "P1 - Critical", etc. |

## Task Sizing

**Too Large (> 3 days)**
- Hard to estimate accurately
- Difficult to track progress
- Risk of getting blocked

**Right Size (1-2 days)**
- Concrete and actionable
- Progress visible daily
- Easier to unblock

**Too Small (< 2 hours)**
- Overhead from task management
- Discourages good estimates
- Creates task clutter

## Task Types

### Backend Implementation
```
Task: Implement [feature] endpoint

Acceptance Criteria:
- [ ] Endpoint accepts [inputs]
- [ ] Returns [format] with [fields]
- [ ] Validates [constraints]
- [ ] Handles [error cases]
- [ ] Tests cover [coverage level]%
```

### Frontend Implementation
```
Task: Build [component/page]

Acceptance Criteria:
- [ ] Component renders [expected layout]
- [ ] Responds to [user interactions]
- [ ] Displays [content] from API
- [ ] Works on [screen sizes]
- [ ] Accessible (WCAG [level])
```

### Database/Data
```
Task: Create [schema/migration]

Acceptance Criteria:
- [ ] Schema supports [use cases]
- [ ] Indexes created for [queries]
- [ ] Migration handles [data]
- [ ] Rollback plan documented
- [ ] Performance tested
```

### Testing
```
Task: Test [feature/component]

Acceptance Criteria:
- [ ] Unit tests: [X]% coverage
- [ ] Integration tests for [scenarios]
- [ ] End-to-end tests for [flows]
- [ ] Performance tests meet [targets]
- [ ] Documented edge cases
```

### Documentation
```
Task: Document [feature/API]

Acceptance Criteria:
- [ ] API documentation complete
- [ ] Usage examples included
- [ ] Edge cases documented
- [ ] Links to related docs added
- [ ] Reviewed and approved
```

## Dependency Mapping

**Identify blocking dependencies:**

```
Auth Implementation (5 days)
├── Database schema (2 days) ← Must happen first
├── API endpoint (3 days) ← Depends on schema
├── Frontend UI (2 days) ← Depends on endpoint
└── Testing (2 days) ← Depends on frontend
```

**Critical Path:** Schema → Endpoint → Frontend → Testing (11 days)

**Parallel Work:** Multiple features can start once dependencies met

## Effort Estimation

**Estimation Techniques:**

1. **Story Points** (Fibonacci: 1, 2, 3, 5, 8, 13)
   - Relative sizing
   - Good for iterative planning
   - Accounts for uncertainty

2. **Hours** (for precise tracking)
   - 4-6 hours = Small task
   - 8-16 hours = Medium task
   - 16+ hours = Break down further

3. **Days** (for roadmapping)
   - 1 day = Sprint task
   - 2-3 days = Normal task
   - 4+ days = Risky, reconsider

## Acceptance Criteria Format

**Good Acceptance Criteria:**
```
Given [context]
When [action happens]
Then [expected result]
```

**Example:**
```
Given user is on the login page
When they enter email and click submit without password
Then they see error "Password is required"
```

## Common Decomposition Patterns

### By Component
- Task 1: Implement backend service
- Task 2: Build UI component
- Task 3: Integrate frontend to backend
- Task 4: Test end-to-end

### By Feature Slice
- Task 1: Happy path implementation
- Task 2: Error handling
- Task 3: Edge cases
- Task 4: Performance optimization

### By Layer
- Task 1: Database layer
- Task 2: API layer
- Task 3: Frontend layer
- Task 4: Integration & testing

### By Priority
- Task 1: MVP features
- Task 2: Core features
- Task 3: Nice-to-haves
- Task 4: Future enhancements

## Red Flags

⚠️ **Task is too vague**
- "Fix authentication" → Break down to specific changes

⚠️ **Task has unclear owner**
- Ensure one person is clearly responsible

⚠️ **Task has no acceptance criteria**
- Add specific, measurable completion definition

⚠️ **Task is estimated at 13+ points**
- Break into smaller tasks

⚠️ **Task has unidentified dependencies**
- List all blockers explicitly

⚠️ **Task depends on another task being done**
- Create clear sequence or parallelize where possible

## Task Lifecycle

```
Spec Analysis
↓
Task Identification
↓
Dependency Mapping
↓
Prioritization & Sequencing
↓
Estimation
↓
Assignment
↓
Implementation (with daily progress)
↓
Review & Testing
↓
Completion & Documentation
```

## Documentation in Task Manager

Each task should link to:
- [ ] Original specification
- [ ] Related tasks
- [ ] Design documentation
- [ ] Test cases
- [ ] Code review URL
- [ ] Merged PR/commit
