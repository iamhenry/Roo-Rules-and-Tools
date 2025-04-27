# Task Analysis
==========================
1. Start with `AnalyzeUserQuery` to evaluate user input for clarity, scope, and context:
   - Input: <User query text>
   - Output: [Clarity, Scope, Context, Suggested clarifications]
   - Action: If any output is negative (N), return clarifications and halt further steps until resolved.

2. Run `AssessTaskComplexity` to evaluate complexity, and risk:
   - Input: <Task description>
   - Output: [Pattern Recognition, Complexity, Risk, Files, Thinking System]
   - Action: Use outputs to decide whether System 1 or System 2 thinking applies.

3. Proceed to `EvaluateTaskModularity` to assess modularity, simplicity, and reusability:
   - Input: <Task description>
   - Output: [Task Independence, Reusability, Interdependencies, KISS Compliance, DRY Compliance, Suggestions]
   - Action: Note any low modularity areas and flag them for improvement.

4. Combine outputs from all tools:
   - IMPORTANT: For each step, mention whether the tool is applied and justify any steps that are skipped, so I can verify that the reasoning is sound and complete.
   - Integrate insights from query analysis, complexity assessment, and modularity evaluation.
   - Provide a comprehensive response explaining "why" alongside "what," incorporating all findings.

5. Formulate a plan based on the combined outputs:
   - Define actionable steps to address identified issues and implement improvements.
   - Ensure the plan aligns with project goals and best practices.
   - Ensure the plan is SMART (Specific, Measurable, Achievable, Relevant, Time-bound)