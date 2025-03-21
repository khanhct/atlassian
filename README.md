# Atlassian Async Client

A modern, async Python client for Atlassian products (Jira and Confluence) with comprehensive API coverage, type safety, and Pydantic models.

## ✨ Features

- 🚀 **Full Async Support**: Built with `httpx` for modern async/await operations
- 🔒 **Type Safety**: Complete type hints and mypy strict mode compliance
- 📦 **Modern Packaging**: Uses `pyproject.toml` and modern Python packaging standards
- 🏗️ **Pydantic Models**: Robust data validation and serialization
- 🔍 **Comprehensive Coverage**: Support for both Jira and Confluence APIs
- ☁️ **Flexible Authentication**: Supports both Cloud and Server/Data Center deployments
- 🔄 **Content Processing**: Built-in preprocessing for Jira and Confluence content
- 📝 **Rich Text Support**: Markdown to Confluence conversion utilities

## 🛠️ Installation

```bash
# Using pip
pip install atlassian-async-client

# Using uv (recommended)
uv pip install atlassian-async-client
```

For development:
```bash
uv pip install -e ".[dev]"
```

## 🚀 Quick Start

### Basic Usage

```python
import asyncio
from atlassian_client import AtlassianClient

async def main():
    async with AtlassianClient(
        base_url="https://your-domain.atlassian.net",
        username="your-email@example.com",
        api_token="your-api-token"
    ) as client:
        # Your API calls here
        pass

if __name__ == "__main__":
    asyncio.run(main())
```

### Environment Configuration

Set up your environment variables:
```bash
# For Cloud deployment
export JIRA_URL="https://your-domain.atlassian.net"
export JIRA_USERNAME="your-email@example.com"
export JIRA_API_TOKEN="your-api-token"

# For Server/Data Center
export JIRA_URL="https://jira.your-company.com"
export JIRA_PERSONAL_TOKEN="your-personal-access-token"
```

Similar configuration for Confluence:
```bash
export CONFLUENCE_URL="https://your-domain.atlassian.net"
export CONFLUENCE_USERNAME="your-email@example.com"
export CONFLUENCE_API_TOKEN="your-api-token"
```

## 📚 Documentation

### Jira Client

```python
from atlassian_client import JiraClient
from atlassian_client.models.jira import JiraIssue

async with JiraClient() as jira:
    # Create issue
    issue = await jira.create_issue(
        project_key="PROJ",
        summary="Test Issue",
        description="Description"
    )
```

### Confluence Client

```python
from atlassian_client import ConfluenceClient
from atlassian_client.models.confluence import ConfluencePage

async with ConfluenceClient() as confluence:
    # Create page
    page = await confluence.create_page(
        space_key="SPACE",
        title="Page Title",
        body="Content"
    )
```

## 🧪 Development

1. Clone the repository:
```bash
git clone https://github.com/khanhct/atlassian-async-client.git
cd atlassian-async-client
```

2. Create virtual environment and install dependencies:
```bash
uv venv
uv pip install -e ".[dev]"
```

3. Run tests:
```bash
pytest
```

4. Code quality:
```bash
# Format code
black .
isort .

# Type checking
mypy .

# Linting
ruff .
```

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built on top of the [atlassian-python-api](https://github.com/atlassian-api/atlassian-python-api) package
- Uses [Pydantic](https://docs.pydantic.dev/) for data validation
- Powered by [httpx](https://www.python-httpx.org/) for async HTTP requests