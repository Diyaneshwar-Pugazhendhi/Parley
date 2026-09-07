# Contributing to ai-chatbot

Thank you for your interest in contributing to **ai-chatbot**! This document outlines the process for setting up a development environment and contributing to the project.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Prerequisites](#prerequisites)
- [Setup Options](#setup-options)
  - [Option 1: Local Development with venv](#option-1-local-development-with-venv)
  - [Option 2: Docker Development](#option-2-docker-development)
- [Project Structure](#project-structure)
- [Development Workflow](#development-workflow)
- [Code Style](#code-style)
- [Testing](#testing)
- [Linting](#linting)
- [Pull Requests](#pull-requests)
- [Reporting Issues](#reporting-issues)

## Code of Conduct

By participating in this project, you agree to uphold the standards described in the [Contributor Covenant](https://www.contributor-covenant.org/). Be respectful and constructive in all interactions.

## Getting Started

### Prerequisites

Ensure you have the following installed on your machine:

- **Python 3.9+** — https://www.python.org/downloads/
- **pip** (bundled with Python 3.4+)
- **Git** — https://git-scm.com/
- **Docker & Docker Compose** *(optional, for containerized development)* — https://docs.docker.com/get-docker/
- **An Anthropic API key** — https://console.anthropic.com/ (required to test the chat functionality)

### Option 1: Local Development with venv

1. **Fork the repository**

   Click the "Fork" button at the top of the [ai-chatbot GitHub page](https://github.com/Diyaneshwar-Pugazhendhi/ai-chatbot).

2. **Clone your fork locally**

   ```bash
   git clone https://github.com/<your-username>/ai-chatbot.git
   cd ai-chatbot
   ```

3. **Create and activate a virtual environment**

   ```bash
   python3 -m venv venv
   source venv/bin/activate      # On Windows: venv\Scripts\activate
   ```

4. **Install dependencies**

   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

5. **Set the Anthropic API key**

   Create a `.env` file at the project root (copy from `.env.example` if available):

   ```bash
   export ANTHROPIC_API_KEY=your_api_key_here
   ```

   Alternatively, install `python-dotenv` (already in `requirements.txt`) and store it in `.env`.

6. **Run the application**

   ```bash
   python app.py
   ```

   The API will be available at `http://localhost:8000`.

### Option 2: Docker Development

If you prefer a containerized setup:

1. **Clone and build the image**

   ```bash
   git clone https://github.com/<your-username>/ai-chatbot.git
   cd ai-chatbot
   docker-compose up -d --build
   ```

2. The container will start on port `8000`. View logs with:

   ```bash
   docker-compose logs -f
   ```

3. To stop and clean up:

   ```bash
   docker-compose down
   ```

## Project Structure

```
ai-chatbot/
├── app.py              # Main Flask application
├── requirements.txt    # Python dependencies
├── Dockerfile          # Docker configuration
├── docker-compose.yml  # Docker Compose configuration
├── .dockerignore       # Docker ignore rules
├── .gitignore          # Git ignore rules
├── CHANGELOG.md        # Change log
├── README.md           # This file
├── CONTRIBUTING.md     # This file
└── .github/            # CI/CD and issue templates
    ├── ISSUE_TEMPLATE/
    │   ├── bug_report.md
    │   └── feature_request.md
    ├── PULL_REQUEST_TEMPLATE.md
    └── workflows/
        └── ci.yml
```

## Development Workflow

1. **Create a branch** for your feature or bug fix:

   ```bash
   git checkout -b feature/my-feature
   ```

2. **Make your changes** and commit frequently with clear messages.

3. **Run the tests and linter** (see below) to ensure everything passes.

4. **Push your branch** and open a pull request.

## Code Style

- Follow [PEP 8](https://peps.python.org/pep-0008/) for Python code.
- Use meaningful variable and function names.
- Keep functions short and focused on a single responsibility.
- Include docstrings for public classes and functions.
- Run `flake8` before committing (configured in CI).

## Testing

This project uses `pytest`. Tests are expected to be placed in a `tests/` directory.

To run tests locally:

```bash
pip install pytest
pytest tests/ -v
```

If no tests exist yet, consider adding them for any new endpoints or logic.

## Linting

Install and run `flake8` to catch style issues:

```bash
pip install flake8
flake8 app.py --max-line-length=100
```

CI will enforce a `max-line-length` of `100`.

## Pull Requests

1. Ensure your branch is up to date with the base branch (`main`):

   ```bash
   git checkout main
   git pull origin main
   git checkout feature/my-feature
   git merge main
   ```

2. Push your branch:

   ```bash
   git push origin feature/my-feature
   ```

3. Open a pull request against the `main` branch and fill out the template.

4. Link any related issues in the PR description using `Closes #<issue-number>`.

## Reporting Issues

Use the provided issue templates:

- **Bug report** — for bugs or unexpected behavior.
- **Feature request** — for new features or enhancements.

Thank you for contributing!
