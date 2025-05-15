---
description: Tool for evaluating task complexity, risk, and determining thinking approach
alwaysApply: false
---

<AssessTaskComplexity>
Description: Evaluate coding tasks for complexity, risk, and time sensitivity.
Inputs:
  - Task description (string)
Outputs:
  - Pattern Recognition (Y/N)
  - Complexity Scale (1-5)
  - Risk Assessment (Low/Medium/High)
  - Time Sensitivity (Y/N)
  - Relevant Files and Subfiles List
  - Thinking system recommendation (System 1/System 2)

Rules:
   1. Assess:
      - Pattern Recognition: Is this a known pattern? (Y/N)
      - Complexity Scale: Rate task complexity (1-5).
      - Risk Assessment: Evaluate impact (Low/Medium/High).
      - Time Sensitivity: Is an immediate response crucial? (Y/N).
      - Files/Subfiles: List affected files.
   2. Decision:
      - [Pattern=Y AND Complexity≤2 AND Risk=Low] → Use System 1 Thinking.
      - [Any(Pattern=N, Complexity>2, Risk≥Medium)] → Use System 2 Thinking.
   3. Always explain the "why" alongside the "what" in your responses.
</AssessTaskComplexity>