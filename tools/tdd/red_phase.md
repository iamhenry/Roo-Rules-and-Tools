---
description: Guidelines for implementing the "Red" phase of Test-Driven Development
alwaysApply: false
---

<tdd-red-phase>

### Pre-requisites  
Before writing tests, ensure the necessary test infrastructure exists:  

1. Check for existing components:  
   - Test utilities and helpers  
   - Mock implementations  
   - Data builders/factories  
   - Shared fixtures  

2. Create missing components if needed:  
   - TestHelpers/ → Shared utilities  
   - Mocks/ → Test doubles  
   - Fixtures/ → Shared test data  
   - Builders/ → Data construction  

---

## Red Phase Workflow  

### 1. Analyze Gherkin Scenarios  
- Identify key behaviors to test (e.g., "When X happens, Then Y occurs").  

### 2. Set Up Minimal Test Infrastructure  
- Add mocks, fixtures, and helpers only as needed for the behavior being tested.  
- Ensure Proper Setup and Isolation: Use minimal dependencies, mocking only components directly impacting the behavior. Keep tests independent with fresh instances of objects or state each time.  

### 3. Write Unit Tests with Guard Rails  
- Focus on observable behavior, not implementation details.  
- Use Dynamic, Flexible Assertions: Base assertions on expected behavior, avoiding hardcoded values. Calculate results dynamically (e.g., using formulas or relative values) rather than assuming fixed outputs.  
- Avoid over-specification unless critical.  
- Use dependency injection and interfaces for dependencies.  
- Use descriptive names → `test[Scenario]_[Condition]_[ExpectedResult]`.  
- Test one behavior per test, avoiding multiple unrelated assertions.  
- Ensure tests are isolated with no shared state.  
- Keep setup minimal and relevant.  
- Handle Asynchronous Behavior: Account for delays or side effects by waiting for async operations to complete (e.g., using `waitFor` or similar tools) before asserting results.  

### 4. File Handling  
- Use `write_to_file` for new test files.  
- Use `apply_diff` to update existing test files (`.test.(js|tsx|ts)`).  

### 5. Verify Failure  
- Verify Test Failure for the Right Reason: Ensure tests fail because the functionality isn't implemented (e.g., assertion fails), not due to setup errors or unexpected runtime issues (e.g., "undefined is not a function"). Define placeholders (e.g., empty functions) if needed to prevent unrelated failures.  
- Run tests using `execute_command` to confirm they fail correctly.  

---

## 6. Evaluate Tests with Guard Rails Checklist  

### Scoring System  
Start at 100 points, deduct for violations:  

#### Maintainability  
- Tests target behavior (Critical, -30)  
- No over-specification (Moderate, -15)  
- Dependencies use interfaces (Moderate, -15)  
- Dynamic assertions used (Moderate, -15)  

#### Clarity  
- Descriptive names (Moderate, -15)  
- One behavior per test (Moderate, -15)  

#### Isolation  
- Isolated tests (Critical, -30)  
- Minimal setup (Minor, -5)  
- Proper async handling (Moderate, -15)  

### Reporting  
Provide a score breakdown for each category and overall (e.g., "Maintainability: 85").  
Use severity indicators:  
- 🟢 (90-100)  
- 🟡 (70-89)  
- 🔴 (<70)  

List violations with severity and deduction (e.g., "Over-specification (-15)").  

---

### 7. Complete the Red Phase  
- Use `attempt_completion` to finalize the Red phase only when tests fail for the right reasons and meet guardrail standards, reducing the need for back-and-forth revisions.
</tdd-red-phase>