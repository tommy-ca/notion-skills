# Knowledge Capture - Evaluation Scenarios

This directory contains test scenarios for validating the Knowledge Capture skill across different Claude models.

## Overview

These evaluations ensure that Knowledge Capture works consistently and effectively with:
- Claude 3 Haiku
- Claude 3 Sonnet
- Claude 3 Opus

Each scenario includes:
- **Input**: The conversation or content to capture
- **Expected Behavior**: What the skill should do
- **Success Criteria**: How to verify success

## Running Evaluations

### Manual Testing

1. Copy the conversation/input from a scenario
2. Activate Knowledge Capture skill in Claude Code
3. Request to capture it as specified
4. Evaluate against the success criteria

### Test Coverage

- Basic conversation capture
- Different documentation types
- Complex multi-topic discussions
- Action item extraction
- Decision documentation
- Error handling

## Scenarios

### scenario-1-meeting-notes.json
**Type**: Meeting Summary Capture
**Complexity**: Medium
**Input**: Unstructured meeting notes from a team discussion
**Expected Output**: Structured meeting summary with decisions and action items
**Success Criteria**: All action items identified, decisions documented, participants listed

### scenario-2-architecture-discussion.json
**Type**: Decision Record Capture
**Complexity**: Medium-High
**Input**: Complex technical architecture discussion
**Expected Output**: Decision record with options considered and rationale
**Success Criteria**: All alternatives documented, clear decision stated, consequences identified

### scenario-3-quick-context.json
**Type**: Quick Capture
**Complexity**: Low
**Input**: Brief status update
**Expected Output**: Quick reference document
**Success Criteria**: Key points captured, properly formatted

### scenario-4-action-items-focus.json
**Type**: Action Item Extraction
**Complexity**: Medium
**Input**: Meeting with many scattered action items
**Expected Output**: Clear list of who, what, when
**Success Criteria**: All action items found, owners assigned, deadlines noted

### scenario-5-learning-from-incident.json
**Type**: Learning Document
**Complexity**: High
**Input**: Post-incident discussion about what went wrong
**Expected Output**: Learning document with best practices
**Success Criteria**: Root causes identified, lessons extracted, preventive measures noted

## Evaluation Criteria

### Comprehensiveness
- Did the skill capture all key information?
- Were important details missed?
- Is the output complete?

### Structure
- Is the output well-organized?
- Are headings and sections appropriate?
- Does it follow the documentation type's structure?

### Actionability
- Are action items clear and assignable?
- Are next steps defined?
- Can someone understand what to do next?

### Linking
- Are cross-references included?
- Could this be discovered from related docs?
- Are important connections made?

### Accuracy
- Is the captured information accurate?
- Were details misinterpreted?
- Does it faithfully represent the source?

## Model-Specific Notes

### Haiku
- May need slightly more structured input
- Evaluates on accuracy and completeness
- Good for quick captures

### Sonnet
- Handles complex discussions well
- Good at inferring structure
- Balanced performance across all scenario types

### Opus
- Excels at inferring structure from unstructured input
- Best for complex, multi-topic discussions
- Highest accuracy on nuanced extraction

## Failure Modes to Watch For

1. **Orphaning**: Documentation created without linking to hub pages
2. **Structure Loss**: Loss of hierarchical organization
3. **Missing Details**: Key decisions or action items not captured
4. **Wrong Type**: Documentation created as wrong type (e.g., FAQ instead of Decision Record)
5. **Broken Context**: Missing important contextual information
6. **Inaccuracy**: Misinterpretation of what was discussed

## Updating Scenarios

When updating scenarios:
1. Ensure they reflect real-world use cases
2. Include edge cases and challenging inputs
3. Keep success criteria clear and measurable
4. Test with all three model sizes
5. Document any model-specific behavior

## Expected Performance

**Target Success Rate**: 90%+ on Sonnet and Opus, 85%+ on Haiku

When a scenario fails:
1. Review the specific failure mode
2. Check if it's a consistent issue or model-specific
3. Update the skill prompt if needed
4. Document the failure and resolution
