---
description: Tool for generating Behavior-Driven Development test scenarios
alwaysApply: false
---

<GenerateBDDTestScenarios>
When generating files, use the following format: `bdd-[filename].md`
Description: Write Behavior-Driven Development (BDD) requirements in the Given-When-Then format for this feature:

```markdown
Output Format:

## Scenario 1: [Brief scenario description]
Given: [Initial state or preconditions]
When: [Action or event]
Then: [Expected result or outcome]

Acceptance Criteria:
- [ ] [Criteria description]
```
Rules:
- Include only the most critical scenarios that define the fundamental behavior of the feature.
- Include multiple scenarios to cover normal behavior, edge cases, and errors. 
- Ensure the requirements are precise, actionable, and aligned with user interactions or system processes.
- Omit irrelevant scenarios.
</GenerateBDDTestScenarios>