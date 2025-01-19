
# GitHub Repository Analysis Agent

An AI-powered CLI tool that enables natural conversation with GitHub repositories, allowing users to explore and understand codebases through simple questions and commands.

## Features

- 🤖 Natural language interaction with GitHub repositories
- 📁 Automatic repository structure analysis
- 📊 Repository metadata and statistics
- 📝 File content access and analysis
- 🔄 Support for both main/master branch conventions
- 🔑 Authentication support for private repositories

## Prerequisites

- Python 3.8+
- GitHub Personal Access Token (for private repositories)
- OpenRouter API Key

## Installation

1. Clone the repository:
```bash
git clone <your-repo-url>
cd github-analysis-agent
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

## Configuration

1. Create a `.env` file in the root directory with the following variables:
```env
GITHUB_TOKEN=your_github_personal_access_token
OPEN_ROUTER_API_KEY=your_openrouter_api_key
LLM_MODEL=deepseek/deepseek-chat  # or your preferred model
```

Required environment variables:
- `GITHUB_TOKEN`: GitHub Personal Access Token (required for private repositories)
- `OPEN_ROUTER_API_KEY`: API key from OpenRouter
- `LLM_MODEL`: LLM model to use (defaults to 'deepseek/deepseek-chat')

## Usage

1. Start the CLI:
```bash
python CLI.py
```

2. Enter your queries in natural language. Examples:
```
> Tell me about this repository
> What's the structure of the main directory?
> Show me the content of the README file
> What are the key files in this project?
```

3. Type 'quit' to exit the application.

## Project Structure

```
├── CLI.py                 # Main CLI interface
├── github_agent.py        # Core agent implementation
├── requirements.txt       # Project dependencies
└── .env                  # Environment configuration
```

## Features in Detail

### Repository Information
- Basic metadata (size, description, stars)
- Language statistics
- Creation and update timestamps

### Structure Analysis
- Directory hierarchy visualization
- File listing with type indicators
- Exclusion of common unnecessary directories (node_modules, __pycache__, .git)

### File Content Access
- Raw file content retrieval
- Support for multiple file types
- Branch-aware content fetching

## Development

The project uses several key dependencies:
- `pydantic-ai`: For AI model integration
- `httpx`: For async HTTP requests
- `python-dotenv`: For environment management
- `logfire`: For logging configuration

## Error Handling

The agent includes robust error handling for:
- Invalid GitHub URLs
- Missing repositories
- Authentication failures
- Rate limiting
- Branch differences (main/master)
