# gh-agent

A custom GitHub Copilot agent framework for learning and exploring the capabilities of AI-powered development tools. This project serves as a comprehensive playground for understanding and implementing custom GitHub Copilot agent behaviors.

## Overview

`gh-agent` is a Python-based project that leverages the **GitHub Copilot SDK** to create customizable agent workflows. It's designed for developers who want to:

- Learn how GitHub Copilot agents work under the hood
- Experiment with custom agent configurations
- Prototype new AI-assisted development patterns
- Build intelligent agents for specific coding tasks
- Explore advanced SDK features in a controlled environment

## Features

- 🤖 **Custom Agent Framework** - Build and configure tailored GitHub Copilot agents
- 🧪 **Experimental Playground** - Safe environment to test new ideas and patterns
- 📚 **Learning-Focused** - Well-documented code designed to educate and inform
- 🔧 **SDK Integration** - Direct integration with the GitHub Copilot SDK
- 🐍 **Modern Python** - Built with Python 3.12+ for modern language features

## Prerequisites

- **Python 3.12** or higher
- **Poetry** (for dependency management)
- **GitHub Copilot SDK** (automatically installed via dependencies)

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/shacharCaduri/gh-agent.git
   cd gh-agent
   ```

2. **Install dependencies using Poetry:**
   ```bash
   poetry install
   ```

3. **Activate the virtual environment:**
   ```bash
   poetry shell
   ```

## Project Structure

```
gh-agent/
├── src/
│   └── agent/              # Main agent package
├── pyproject.toml          # Project configuration and dependencies
├── poetry.lock             # Locked dependency versions
└── README.md               # This file
```

## Dependencies

- **github-copilot-sdk** (>=0.1.25, <0.2.0) - Official GitHub Copilot SDK for Python

See `pyproject.toml` for the complete dependency specification.

## Getting Started

### Basic Usage

```python
# Example: Initialize and work with a custom agent
from agent import YourAgentClass

# Create your custom agent
agent = YourAgentClass()

# Use the agent for your tasks
result = agent.process()
```

### Development Workflow

1. **Create agent implementations** in `src/agent/`
2. **Test your implementations** with pytest or your preferred test framework
3. **Experiment with SDK features** in an interactive environment
4. **Document your findings** and patterns

## Configuration

Configure your agent by modifying the appropriate configuration files or environment variables. Refer to the GitHub Copilot SDK documentation for available configuration options.

## API Reference

The main API is exposed through the `agent` module. Key components include:

- Agent classes for various use cases
- Configuration and setup utilities
- Integration helpers for Copilot SDK

For detailed API documentation, see the docstrings in the source code.

## Learning Resources

- [GitHub Copilot SDK Documentation](https://docs.github.com/en/copilot)
- Official SDK examples and tutorials
- Source code comments and docstrings
- This project's own implementation patterns

## Use Cases

- **Rapid Prototyping** - Quickly test agent concepts and behaviors
- **Educational** - Learn about AI agent architecture and SDK usage
- **Experimentation** - Safely explore new features and patterns
- **Custom Workflows** - Develop specialized agents for specific domains
- **Integration Testing** - Validate SDK integration patterns

## Contributing

This is a personal learning and playground project. Feel free to:

- Experiment with different approaches
- Document your learnings
- Refactor and improve code
- Try new patterns and techniques

## Troubleshooting

### Common Issues

**Issue: Module not found**
- Ensure you've activated the Poetry environment: `poetry shell`
- Reinstall dependencies: `poetry install`

**Issue: Python version mismatch**
- Verify Python 3.12+: `python --version`
- Use `pyenv` or similar tools to manage Python versions

**Issue: SDK compatibility**
- Check the installed SDK version: `poetry show github-copilot-sdk`
- Update if needed: `poetry update github-copilot-sdk`

## Development Tools

### Running Commands

```bash
# Install dependencies
poetry install

# Add new dependencies
poetry add <package-name>

# Run tests (when available)
poetry run pytest

# Build distribution
poetry build
```

## License

This project is provided as-is for learning and experimentation purposes.

## Author

**shacharCaduri** - [@shacharCaduri](https://github.com/shacharCaduri)

## Contact & Support

For questions or discussions about this project:
- 🐙 GitHub: [shacharCaduri](https://github.com/shacharCaduri)
- 📧 Email: [73823590+shacharCaduri@users.noreply.github.com](mailto:73823590+shacharCaduri@users.noreply.github.com)

---

**Status**: Actively maintained for learning and experimentation

**Last Updated**: February 2026