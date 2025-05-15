---
description: Tool for evaluating and clarifying ambiguous user queries
alwaysApply: false
---

<AnalyzeUserQuery>
Description: Evaluate and clarify ambiguous user queries.
Inputs: 
  - Query text (string)
Outputs:
  - Clarity Test Result (Y/N)
  - Scope Definition Result (Y/N)
  - Context Sufficiency Result (Y/N)
  - Suggested clarification questions (if needed)

Rules:
   1. Test for:
      - Clarity: Does the query specify a clear goal? (Y/N)
      - Scope: Is the query narrow and well-defined? (Y/N)
      - Context: Does the query provide enough information? (Y/N)
   2. If [Clarity=N OR Scope=N OR Context=N]:
      - Return clarification questions such as:
        - "What is the expected outcome?"
        - "Do you have specific examples or constraints?"
        - "Are there particular tools or technologies you'd like to use?"
</AnalyzeUserQuery>