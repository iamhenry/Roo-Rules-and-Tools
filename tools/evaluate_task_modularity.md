---
description: Tool for assessing task modularity, simplicity, and code reusability
alwaysApply: false
---

<EvaluateTaskModularity>
Description: Assess coding tasks for modularity, simplicity, and reusability.
Inputs: 
  - Task description (string)
Outputs:
  - Task Independence (Y/N)
  - Reusability Potential (Y/N)
  - Interdependency Check (Y/N)
  - KISS Compliance (Y/N)
  - DRY Compliance (Y/N)
  - Suggested modular improvements (if needed)

Rules:
   1. Test for:
      - Task Independence: Can the task be broken into smaller units? (Y/N)
      - Reusability: Will the output be reusable? (Y/N)
      - Interdependencies: Are dependencies minimal? (Y/N)
      - KISS Principle: Is the task simple? (Y/N)
      - DRY Principle: Does it avoid duplication? (Y/N)
   2. If [Task Independence=N OR KISS=N OR DRY=N]:
      - Suggest improvements:
        - Simplify task structure (KISS).
        - Eliminate code duplication (DRY).
        - Reduce interdependencies.
</EvaluateTaskModularity>