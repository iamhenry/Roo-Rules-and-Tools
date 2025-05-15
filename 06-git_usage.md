---
description: Defines Git commit message format, types, and scope conventions
alwaysApply: true
---

# Git Usage
==========================
IMPORTANT: Use concise but context-rich messages. Start with a brief summary of the changes followed by a bulleted list of each change.
Use the following prefixes for commit messages:

## Format
```
<type>(<scope>): <subject>
```

## Types
- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation only changes
- `style`: Changes that do not affect the meaning of the code (white-space, formatting, etc)
- `refactor`: A code change that neither fixes a bug nor adds a feature
- `perf`: A code change that improves performance
- `test`: Adding missing tests or correcting existing tests
- `chore`: Changes to the build process or auxiliary tools and libraries
- `ci`: Changes to CI configuration files and scripts
- `revert`: Reverts a previous commit

## Scope
- Optional, can be anything specifying the place of the commit change
- Examples: auth, user, dashboard, api, database