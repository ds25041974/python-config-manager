# Advanced Python Project

A modern Python project demonstrating internationalization, template-based text generation, and robust configuration management. Built with comprehensive test coverage and following best development practices.

## Features

- **Multi-language Support**: 
  - Support for English, Spanish, French, German, and Japanese
  - Language-specific translations for messages and errors
  - Easy addition of new languages

- **Template System**:
  - Multiple greeting templates (formal, casual, funny, business)
  - Template categorization and tagging
  - Template metadata with descriptions
  - Search templates by category or tags

- **Configuration Management**:
  - JSON-based configuration files
  - Environment-specific settings
  - Validation with proper error handling
  - Debug and logging configuration
  - Timezone and rate limiting settings

- **CLI Interface**:
  - Rich command-line interface with subcommands
  - Support for sync and async operations
  - Multiple output template styles
  - Debug mode with enhanced logging
  - Configuration file management

## Project Structure

```
.
├── src/
│   ├── main.py              # CLI and core functionality
│   └── config/
│       ├── i18n.py          # Internationalization
│       ├── settings.py      # Configuration handling
│       ├── templates.py     # Template management
│       └── validation.py    # Config validation
├── tests/                   # Test files
├── .github/                 # GitHub workflows
├── pyproject.toml          # Project configuration
└── # ConfigMaster: Advanced Python Configuration Management System

## Project Overview

ConfigMaster is a robust, enterprise-grade configuration management system built in Python that provides advanced features for handling application settings, internationalization, templating, and validation. This project demonstrates modern Python development practices and integrates with Model Context Protocol (MCP) servers for enhanced functionality.

## Key Features

- **Strong Type Validation**: Runtime type checking and validation of configuration values
- **Internationalization (i18n)**: Built-in support for multiple languages (EN, ES, FR, JA)
- **Template Management**: Flexible template system with categorization and tagging
- **Configuration Persistence**: JSON-based storage with automatic validation
- **Async Support**: Asynchronous operations for performance-critical applications
- **Comprehensive Testing**: 100% test coverage with pytest
- **MCP Server Integration**: Enhanced capabilities through Model Context Protocol

## MCP Server Integration

### What is MCP (Model Context Protocol)?

The Model Context Protocol (MCP) is a sophisticated communication protocol that enables seamless integration between development tools, AI assistants, and various services. In this project, we utilize MCP servers for:

1. **GitHub Integration**
   - Repository management
   - Code synchronization
   - Automated workflows
   - Collaboration features

2. **Azure Services** (Optional Extension)
   - Cloud configuration management
   - Service deployment
   - Resource monitoring
   - Security compliance

3. **Development Tools**
   - Code analysis
   - Documentation generation
   - Quality assurance
   - Performance monitoring

### Benefits of MCP Server Integration

1. **Enhanced Development Workflow**
   - Automated code reviews
   - Intelligent code suggestions
   - Context-aware assistance
   - Integrated version control

2. **Improved Code Quality**
   - Real-time validation
   - Best practice enforcement
   - Automated testing
   - Security scanning

3. **Streamlined Deployment**
   - Automated builds
   - Environment consistency
   - Configuration validation
   - Rollback capabilities

4. **Team Collaboration**
   - Code sharing
   - Knowledge management
   - Project synchronization
   - Change tracking

## Installation

```bash
# Clone the repository
git clone https://github.com/ds25041974/python-config-manager.git

# Create and activate virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -e ".[dev]"
```

## Usage Examples

### Basic Configuration

```python
from src.config.settings import AppConfig
from src.config.i18n import Language

# Create configuration with custom settings
config = AppConfig(
    debug=True,
    language=Language.JA,
    custom_message="Welcome to ConfigMaster!"
)

# Validate and save configuration
config.validate()
config.to_file("config.json")
```

### Template Management

```python
from src.config.templates import TemplateManager, TemplateCategory

# Get templates by category
formal_templates = TemplateManager.get_by_category(TemplateCategory.FORMAL)

# Search templates by tags
business_templates = TemplateManager.search_by_tags({"business", "professional"})
```

### Internationalization

```python
from src.config.i18n import get_translation, Language

# Get translations for different languages
en_trans = get_translation(Language.EN)
ja_trans = get_translation(Language.JA)

print(en_trans.greeting_prefix)  # "Hello"
print(ja_trans.greeting_prefix)  # "こんにちは"
```

## Project Structure

```
src/
├── config/
│   ├── i18n.py        # Internationalization support
│   ├── settings.py    # Configuration management
│   ├── templates.py   # Template system
│   └── validation.py  # Validation logic
├── main.py           # Main application entry
tests/
└── test_main.py     # Comprehensive tests
```

## Development

### Running Tests

```bash
# Run all tests
pytest tests/

# Run tests with coverage
pytest --cov=src tests/

# Run specific test
pytest tests/test_main.py -k "test_greet_with_language"
```

### Code Quality

```bash
# Format code
black .
isort .

# Type checking
mypy src tests

# Linting
flake8 .
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Run tests and ensure code quality
5. Submit a pull request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- Python community for best practices and patterns
- MCP server developers for protocol specifications
- Contributors to dependent libraries

## Support

For questions and support:
- Open an issue on GitHub
- Contact the development team
- Check documentation updates               # This file
```

## Installation

1. Create a virtual environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows use: .venv\Scripts\activate
   ```

2. Install dependencies:
   ```bash
   pip install -e ".[dev]"
   ```

## Usage

### Basic Greeting

```bash
# English greeting
python -m src.main greet "World"

# Spanish greeting
python -m src.main greet "World" --language es

# Formal style in French
python -m src.main greet "World" --language fr --style formal

# Custom message in Japanese
python -m src.main greet "World" --language ja --message "おはようございます"
```

### Template Management

```bash
# List all templates
python -m src.main templates

# List formal templates
python -m src.main templates --category formal

# Search by tags
python -m src.main templates --tags "business,polite"
```

### Configuration

```bash
# View current config
python -m src.main config view

# Validate config file
python -m src.main config validate --file config.json

# Save current settings
python -m src.main greet "World" --debug --style formal --save-config config.json
```

## Development

This project uses modern Python development tools for quality and consistency:

- **Type Hints**: All code is type-annotated and checked with mypy
- **Documentation**: Google-style docstrings
- **Testing**: pytest with async support and coverage reporting
- **Code Quality**: 
  - black for formatting
  - isort for import sorting
  - flake8 for linting
  - mypy for type checking
  - pre-commit hooks for consistent style

### Running Tests

```bash
# Run all tests
pytest tests/

# Run with coverage
pytest tests/ --cov=src --cov-report=xml
```

### Code Quality

```bash
# Format code
black .
isort .

# Run linting
flake8 .
mypy src tests
```

## CI/CD

The project uses GitHub Actions for continuous integration with:

- Multi-Python version testing (3.8-3.11)
- Code formatting verification
- Type checking
- Linting
- Test coverage reporting
- Automatic coverage upload to Codecov

The workflow runs on:
- Push to main branch
- Pull request to main branch

## Project Conventions

1. Type hints on all functions and classes
2. Google-style docstrings for public APIs
3. Test coverage for new functionality
4. Black code formatting
5. Pre-commit hooks for code quality

## Requirements

- Python 3.8 or higher
- Dependencies listed in pyproject.toml
- Development tools in optional-dependencies.dev