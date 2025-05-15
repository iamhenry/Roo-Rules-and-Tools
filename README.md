---
description: Overview of Roo AI Assistant configuration, tools, and project structure
alwaysApply: false
---

# Roo AI Assistant Configuration & Tools

This repository contains the configuration files, guidelines, and tool descriptions for the Roo AI assistant, designed to aid in various software development tasks within the Cline environment.

## Project Structure

- Root Directory: Contains general guidelines, principles, and configuration files (like `.clinerules`) that define the assistant's behavior and operational context.
  - `coding_principles.md`: Guidelines for code generation.
  - `documentation.md`: Standards for documentation.
  - `git_usage.md`: Best practices for Git usage.
  - `package_install.md`: Notes on package installation.
  - `role.md`: Defines the AI assistant's role.
  - `task_analysis.md`: Principles for analyzing tasks.
  - `tech_stack.md`: Information about the relevant tech stack.
  - `thinking_principles.md`: Guidelines for the AI's thought process.
  - `.clinerules`: Specific rules for the Cline environment, potentially defining custom tool behaviors.

- `tools/` Directory: Contains detailed descriptions and instructions for specific tools and workflows available to the assistant.
  - `README.md`: Overview of the tools directory.
  - Individual `.md` files (e.g., `debug_error.md`, `generate_commit.md`, `propose_solution.md`, `retrospective.md`): Define specific capabilities like debugging, commit message generation, solution proposal, and conducting retrospectives.
  - `tools/tdd/` Subdirectory: Contains resources specifically for Test-Driven Development workflows, including BDD scenario generation, unit test generation, and phase-specific guidelines.

## Key Features

This configuration enables the Roo AI assistant to perform tasks such as:

- Analyzing user queries and task complexity.
- Following specific coding, thinking, and documentation principles.
- Assisting with debugging errors (`DebugError`).
- Proposing technical solutions (`ProposeSolution`).
- Generating documentation (`GenerateDocumentation`).
- Automating Git commit messages (`GenerateCommit`).
- Facilitating retrospectives (`Retrospective`).
- Supporting Test-Driven Development (TDD) workflows.

## Usage

These files are primarily intended to be used by the Cline environment to configure and guide the Roo AI assistant. Refer to the individual markdown files for details on specific tools and processes.