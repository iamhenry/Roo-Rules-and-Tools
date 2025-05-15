---
description: Outlines code quality principles including YAGNI, DRY, KISS, and modularity guidelines
alwaysApply: true
---

# Coding Principles
==========================
- YAGNI (You Aren't Gonna Need It)
- Only implement features that are currently needed
- Avoid speculative functionality
- Remove unused code and commented-out sections
- Focus on readability over being performant
- ALWAYS ensure minimal edits to existing logic
- ALWAYS indent the code blocks
- Always generate descriptive names

### DRY (Don't Repeat Yourself)
- Extract reusable components into separate files
- Use SwiftUI ViewModifiers for common styling
- Create shared utilities for common operations
- Use protocol extensions for shared functionality

### KISS (Keep It Simple, Stupid)
- Prefer simple, clear implementations over complex solutions
- Use descriptive naming that reflects purpose
- Break complex logic into smaller, focused functions
- Minimize state management complexity

## Modularity Guidelines
- Create reusable SwiftUI components for common UI patterns
- Each component should have a single responsibility
- Components should be self-contained with clear interfaces
- Use dependency injection for better testability
- Extract business logic from views into interactors