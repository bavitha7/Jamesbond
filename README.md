# Jamesbond

The `Jamesbond` project is a `crewAI`-based application leveraging AI agents to perform intelligent tasks. Built with Python, it uses the `crewAI` framework to orchestrate agent-based workflows, with support for local models (e.g., Ollama) or OpenAI’s API for advanced capabilities.

## Table of Contents

- Installation
- Configuration
- Usage
- Project Structure
- Contributing
- License

## Installation

### Prerequisites

- Python 3.8+ (3.12 recommended)
- Git
- `uv` (optional, for dependency management)
- Ollama (optional, for local model support)

### Steps

1. **Clone the Repository**

   ```bash
   git clone git@github.com:bavitha7/Jamesbond.git
   cd Jamesbond
   ```

2. **Create a Virtual Environment**

   ```bash
   python3 -m venv reddy
   source reddy/bin/activate
   ```

3. **Install Dependencies**

   - Using `uv` (recommended if `uv.lock` exists):

     ```bash
     pip install uv
     uv sync
     ```
   - Or using `pip`:

     ```bash
     pip install --upgrade pip
     pip install crewai
     ```

4. **Verify Installation**

   ```bash
   pip show crewai
   crewai --version
   ```

## Configuration

Create a `.env` file in the project root to configure the model and API settings:

```bash
nano .env
```

Add one of the following configurations:

- **For OpenAI**:

  ```bash
  API_KEY=your-openai-api-key
  API_BASE=https://api.openai.com/v1
  ```

  Get an API key from OpenAI.

- **For Ollama (Local Model)**:

  ```bash
  MODEL=ollama/llama3.1
  ```
**Note**: Do not commit `.env` to Git. It’s included in `.gitignore`.

## Usage

Run the `crewAI` application:

```bash
crewai run
```

- This executes the main workflow defined in `src/jamesbond/crew.py` or `src/jamesbond/main.py`.
- If prompted for input (e.g., a question), provide it as needed.
- If you encounter a warning like `[WARNING]: Failed to init knowledge: Please provide an OpenAI API key`, ensure your `.env` has a valid `API_KEY` or configure for Ollama.

## Project Structure

```
Jamesbond/
├── reddy/              # Virtual environment
├── src/                # Source code
│   └── jamesbond/
│       ├── crew.py     # CrewAI agent definitions
│       ├── main.py     # Main application script
│       ├── config/     # Configuration files
│       └── tools/      # Custom tools for agents
├── .env                # Environment variables (not committed)
├── .gitignore          # Git ignore file
├── pyproject.toml      # Project metadata and dependencies
├── uv.lock             # Dependency lock file
└── README.md           # This file
```


