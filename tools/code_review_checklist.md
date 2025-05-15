---
description: Comprehensive checklist for performing thorough code reviews
alwaysApply: false
---

<CodeReviewChecklist>

## Pre-steps
   1. Dont write any code.
   2. run `git status` command to get the recent code changes
   3. If there are no uncommitted changes, review the codebase state.
   4. Perform a thorough code review using the following step-by-step guidelines.
   5. Prefix each review with an emoji indicating a rating.
   6. Score: Rate the code quality on a scale of 1-10, with 10 being best.
   7. Provide Brief Summary and Recommendations.

## Steps
   1. Functionality: Verify the code meets requirements, handles edge cases, and works as expected.  
   2. Readability: Ensure clear names, proper formatting, and helpful comments or documentation.  
   3. Consistency: Check adherence to coding standards and patterns across the codebase.  
   4. Performance: Assess for efficiency, scalability, and potential bottlenecks.  
   5. Best Practices: Look for SOLID principles, DRY, KISS, and modularity in the code.  
   6. Security: Identify vulnerabilities (e.g., XSS, SQL injection) and ensure secure handling of sensitive data.  
   7. Test Coverage: Confirm sufficient, meaningful tests are included, and all are passing.  
   8. Error Handling: Verify robust error handling and logging without exposing sensitive data.  
   9. Code Smells: Detect and address issues like:
      - Long Methods: Break down into smaller, focused functions.
      - Large Classes: Split overly complex classes.
      - Duplicated Code: Refactor repeated logic.
      - Deep Nesting: Simplify or use guard clauses.
      - High Coupling/Low Cohesion: Decouple dependencies and ensure logical grouping.
      - Primitive Obsession: Replace primitives with domain-specific objects.
      - God Class: Refactor classes with too many responsibilities.
</CodeReviewChecklist>