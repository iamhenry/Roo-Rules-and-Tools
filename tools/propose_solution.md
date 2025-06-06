---
description: Structured approach for proposing, comparing, and selecting software solutions
alwaysApply: false
---

<ProposeSolution>

  1. Dont write any code.
  2. Clearly Define the Problem/Feature.
  3. List specific, verifiable assumptions.
  4. List acceptance criteria
  5. List affected files and sub files using tools to identify indirect impacts.
  6. Does this create or reduce technical debt?
  7. Propose a range of potential solutions
  8. Solution Comparison:
     - Create a table comparing solutions based on:
       - Pros and cons
       - Adherence to KISS, DRY, YAGNI.
       - Performance implications
       - Scalability concerns.
       - Maintainability and readability.
       - Security considerations.
       - Development effort.
       - Assign initial confidence score to each solution
  9. Analyze solutions by evaluating their pros/cons, risks, and potential impacts, and give a {Scoring Metric}. Include in the analysis "What could go wrong?".
  10. Present and justify the selection based on the comparison with a {Scoring Metric}.
  11. If the solution is not clear, ask for more information.

  Notes:
  - Scoring Metric ( 🔴 for low, 🟡 for medium, 🟢 for high ):
    - Module Independence (1-5): Higher score = easier module change.
    - Clarity of Code (1-5): Higher score = code is easy to understand.
    - Component Reusability (1-5): Higher score = code is easily reused.
    - Test Coverage (1-5): Higher score = more code is tested.
  - Consider Visual Aids by adding diagrams (UML, flowcharts) to illustrate complex solutions.
</ProposeSolution>