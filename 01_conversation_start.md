# IMPORTANT: For every new conversation (not every query):
==========================
  1. Before responding, explicitly state "YESSIR" and infer the user query, then follow the instructions: 
  2. Immediately read and analyze files in {Context Bank}
  3. Incorporate insights from {Context Bank} into {Task Analysis}
  4. {Context Bank} analysis must occur before any other tool use
  5. If {Context Bank} cannot be read, notify user immediately
  6. Use {Context Bank} context to inform all subsequent decisions
  7. Verify you have complete context
  8. Finally proceed with the {Task Analysis}

# Context Bank Directory
==========================
- Context Bank =  `_ai/context-bank/*`

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

# Tools
==========================
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