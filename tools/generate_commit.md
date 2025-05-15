---
description: Tool for generating standardized Git commit messages with proper format and context
alwaysApply: false
---

<GenerateCommit>
## Automating Git Commits for AI-Generated Codebases

### Overview
Automate Git commits for AI-generated code across platforms, triggering on test fail-to-pass transitions. Ensure stability and generate detailed Conventional Commit messages with "what" and "why" using terminal access (e.g., `git`, `npm`), adapting dynamically without config.

---

1. Detect Test Flip
- Goal: Trigger on test fail-to-pass.
- Steps: Check `package.json` `scripts.test` or infer runners (e.g., `jest`, `vitest`, `tuist test`). Monitor watch mode or last manual result for a flip; proceed if detected.
2. Verify Stability
- Goal: Ensure reliability.
- Steps: Confirm test flip. Run `npm run lint` and `tsc --noEmit` if present; skip if either fails. Check `git diff --cached` for untested breaking changes; skip if found. Log "Skipped: <reason>" (e.g., "Linting failed") and exit if unstable.
3. Stage Changes
- Goal: Prepare files.
- Steps: Run `git add .`, verify with `git status --short`.
4. Generate Message
- Goal: Craft detailed commit.
- Steps: Use `git diff --name-only --cached`, `--cached`, and test output to infer type (e.g., `feat`) and scope (e.g., `components`). Format: `<type>(<scope>): <subject>\n\n- What: <Change>\n- Why: <Reason>...`. Example:
  ```
  feat(components): Add new button

  - What: Added Button in src/components/button.js with size props.
  - Why: Enable dynamic size adjustments for a customizable UI.
  - What: Created tests in tests/button.test.js.
  - Why: Ensure reliable rendering and detect potential regressions.
  ```
5. Apply Guardrails
- Goal: Avoid noise.
- Steps: Skip if <5 lines or unrelated to test flip. Log "Skipped: <reason>" (e.g., "Trivial changes") and exit if fails; proceed if passes.
6. Commit
- Goal: Finalize with tag.
- Steps: Tag as `auto-MM-DD-YYYY-HHMM-AM/PM` (e.g., `auto-04-04-2025-0230-PM`). Run `git commit -m "<message>" --tag "<tag>"`.
7. Enable Undo
- Goal: Allow rollback.
- Steps: Log "Committed: <type>(<scope>): <subject> (undo: git undo-auto)". Support `git undo-auto` as `git reset --soft HEAD^`.
</GenerateCommit>