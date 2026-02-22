---
description: General development guidelines and best practices for the gh-agent project
---

# GitHub Copilot Development Instructions

## Project Overview

This is a **gh-agent** project - a custom GitHub Copilot agent framework for learning and experimentation. All work should prioritize clarity, educational value, and maintainability.

## Core Principles

1. **Learning-First Approach**
   - Write code that is easily understandable and well-documented
   - Include comments explaining the "why" not just the "what"
   - Design patterns should be instructive and follow best practices
   - Optimize for readability over cleverness

2. **Code Quality Standards**
   - Follow PEP 8 style guidelines for all Python code
   - Use type hints consistently throughout the codebase
   - Maintain a minimum of 80% test coverage for new features
   - Ensure all code is properly documented with docstrings

3. **Project Maintenance**
   - Keep dependencies up-to-date and documented in `pyproject.toml`
   - Use Poetry for all dependency management
   - Maintain the README.md with accurate, current information
   - Document all new features and changes

4. **Experimentation Philosophy**
   - This is a playground project - new ideas and patterns are encouraged
   - Create feature branches for experimental work
   - Document experiments and findings
   - Share learnings through code comments and documentation

## Development Workflow

### File Organization
- Source code: `src/agent/`
- Tests: `tests/` (create as needed)
- Configuration: `pyproject.toml`
- Documentation: Root level (README.md, etc.)

### Python Standards
- Target: Python 3.12+
- Use modern language features
- Avoid deprecated patterns
- Leverage type hints for better IDE support and documentation

### Documentation Requirements
- All public classes and functions must have docstrings
- Complex logic should include explanatory comments
- README should be kept current with project structure changes

## External Dependencies

### GitHub Copilot SDK
- Treat the SDK as a learning tool
- Understand how to use its core APIs
- Document non-obvious usage patterns
- Share successful integration approaches

### Poetry
- Use Poetry for all dependency management
- Keep `pyproject.toml` as the source of truth
- Lock dependencies in `poetry.lock`
- Document why each dependency is needed

## Code Review Checklist

Before committing, ensure:
- ✅ Code follows PEP 8 style guidelines
- ✅ Type hints are present for function signatures
- ✅ Docstrings are clear and complete
- ✅ Complex logic includes explanatory comments
- ✅ No debug code or print statements left behind
- ✅ Tests pass (if applicable)
- ✅ README.md is still accurate

## Experimentation Guidelines

When trying new approaches:
1. Create a feature branch clearly labeled with the experiment name
2. Document your approach and expectations
3. Record findings and results
4. Merge successful patterns to main, document learnings
5. Close or document unsuccessful experiments

## Git and Version Control

- Commit messages should be clear and descriptive
- Use conventional commit format when significant
- Keep commits atomic and focused
- Reference the `.github/instructions/commits.instructions.md` for commit-specific guidelines

## Performance Considerations

- Profile code before optimizing
- Document any performance-critical sections
- Consider the trade-off between clarity and speed
- For this learning project, clarity usually wins

## Security and Safety

- Never commit credentials or secrets
- Use environment variables for sensitive configuration
- Document all external integrations
- Validate all external inputs

---

**Last Updated**: February 2026

**Maintained By**: shacharCaduri
