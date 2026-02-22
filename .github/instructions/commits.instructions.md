---
description: Guidelines for commit messages, builds, and code integration in the gh-agent project
applyTo: "**/*.py|pyproject.toml|README.md"
---

# Commit and Build Instructions

## Commit Message Standards

### Format: Numbered Conventional Commits

All commits should follow the Conventional Commits specification with a commit number prefix:

```
#<number> commit: <type>(<scope>): <subject>

<body>

<footer>
```

**Commit numbering starts at #1 for the first commit and increments sequentially.**

### Commit Types

- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation changes
- **refactor**: Refactoring code without feature changes
- **test**: Adding or updating tests
- **chore**: Build process, dependencies, tooling
- **style**: Code style changes (formatting, missing semicolons, etc.)
- **perf**: Performance improvements

### Subject Line Rules

- Use imperative, present tense: "add" not "added" or "adds"
- Don't capitalize first letter
- No period (.) at the end
- Maximum 50 characters
- Be specific and descriptive

### Subject Examples

✅ Good:
- `#1 commit: feat(agent): add custom handler initialization`
- `#2 commit: fix(sdk): resolve memory leak in event loop`
- `#3 commit: docs: update installation instructions`
- `#4 commit: refactor(core): simplify agent configuration logic`

❌ Bad:
- `#1 commit: Update code` (too vague)
- `#2 commit: fixed bug` (use "fix:" prefix)
- `#3 commit: Added some features and fixed things` (multiple types)

### Body Content

If a commit needs explanation, include a body:
- Explain what and why, not how
- Separate from subject with a blank line
- Wrap at 72 characters
- Include references to issues/PRs if applicable

### Footer

Include if applicable:
```
Fixes #123
Closes #456
Breaking-Change: description of breaking change
```

## Build and Release Guidelines

### Before Committing

1. **Verify the build locally**
   ```bash
   poetry install
   poetry run pytest  # if tests exist
   ```

2. **Run code quality checks**
   - Use a linter: `poetry run black .` (if configured)
   - Check type hints: `poetry run mypy src/` (if configured)

3. **Update dependencies**
   ```bash
   poetry update  # to check for updates
   poetry lock    # to lock versions
   ```

### Build Process

When making changes to `pyproject.toml`:
- Always test dependency installation: `poetry install`
- Update `poetry.lock`: `poetry lock --no-update`
- Document any new dependencies in the file
- Verify Python version requirements are met

### Testing and Validation

- Write tests for new features when possible
- Ensure existing tests still pass
- Document any breaking changes
- Update the README if adding features

## Commit Frequency and Atomicity

### Keep Commits Atomic

Each commit should:
- Accomplish one logical change
- Be testable/buildable in isolation
- Have a clear purpose

### Good Commit Patterns

✅ One commit per feature/fix:
```
#1 commit: feat(sdk): add custom agent initialization
#2 commit: fix(core): handle edge case in config parsing
#3 commit: docs: update API reference
```

❌ Anti-patterns:
```
wip: everything (incomplete)
temp: debugging code (should be removed)
multiple unrelated changes in one commit
```

## Push and Deployment

### Before Pushing

- [ ] All commits follow conventional format
- [ ] Build and tests pass locally
- [ ] Documentation is updated
- [ ] No debug code or commented code remains
- [ ] Commit messages are clear and descriptive

### Push Command

```bash
git push -u origin <branch-name>
```

For main branch:
```bash
git push -u origin main
```

## Rollback and Corrections

### Fix Incorrect Commits

If a commit message is wrong (before push):
```bash
git commit --amend
```

If commits are already pushed, consider:
- Creating a corrective commit for simple fixes
- Force push only for your own feature branches (never main)

## Integration Guidelines

### Feature Branches

When working on new features:
1. Create a descriptive branch: `feat/agent-initialization`
2. Make logical atomic commits
3. Push with: `git push -u origin feat/agent-initialization`
4. Prepare for pull request with clear commit history

### Main Branch

The main branch should always:
- Have a clean, understandable commit history
- Contain working, tested code
- Have clear commit messages
- Be deployable

## Special Commit Types

### Documentation-Only Commits

```
#5 commit: docs: update README with SDK examples

- Add section on custom agent creation
- Include code examples
- Update troubleshooting section
```

### Dependency Updates

```
#6 commit: chore(deps): update github-copilot-sdk to 0.1.26

- Update poetry lock file
- Test compatibility with existing code
- Document any API changes
```

### Refactoring Commits

```
#7 commit: refactor(core): simplify configuration initialization

Extracted repeated configuration logic into helper function.
No behavioral changes, improved readability.
```

## Commit Inspection Checklist

Before running `git push`, verify each commit:

- [ ] Type prefix is correct (feat/fix/docs/etc)
- [ ] Scope is specific and relevant
- [ ] Subject is clear and descriptive
- [ ] Subject uses imperative mood
- [ ] No period at end of subject
- [ ] Body explains why, not what
- [ ] Related issues are referenced
- [ ] Code changes are logically grouped

## Examples of Well-Formatted Commits

**Example 1: Feature Addition**
```
#1 commit: feat(agent): implement custom event handler system

Add ability for users to register custom event handlers
in the agent configuration. Handlers receive event objects
and can modify agent behavior dynamically.

This enables users to extend agent capabilities without
modifying core code.

Fixes #42
```

**Example 2: Bug Fix**
```
#2 commit: fix(sdk-integration): handle null response from copilot API

The SDK can occasionally return null responses when the API
is under load. Added proper null checking and retry logic
with exponential backoff.

Closes #38
```

**Example 3: Documentation**
```
#3 commit: docs: add SDK integration guide

- Add getting started section
- Include API reference examples
- Document common use cases
- Add troubleshooting section
```

---

**Last Updated**: February 2026

**Purpose**: Maintain clean, understandable, and professional commit history for the gh-agent project
