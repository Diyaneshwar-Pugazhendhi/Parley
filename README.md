# ai-chatbot

An intelligent conversation system built with Flask that demonstrates AI-powered chat capabilities using the Anthropic Claude API. This project showcases a production-ready chatbot with RESTful endpoints, health checks, and scalable deployment via Docker.

![Preview](https://img.shields.io/badge/Powered%20by-Anthropic%20Claude-blue.svg)
![Preview](https://img.shields.io/badge/License-MIT-green.svg)
![Preview](https://img.shields.io/badge/PRs-Welcome-brightgreen.svg)

## 📖 Overview

The **ai-chatbot** is a conversational AI system that provides intelligent responses through a simple REST API. It's designed to be easily integrated into other applications, deployed via Docker, and extended with additional features.

## 🛠 Tech Stack

- **Language**: Python 3
- **Framework**: Flask
- **AI**: Anthropic Claude API
- **Containerization**: Docker & Docker Compose
- **Environment**: Virtual Environment (venv)

## 🚀 Quick Start

### Prerequisites

- Docker & Docker Compose
- Python 3.9+ (optional, for local development)

### Installation

```bash
# Clone the repository
git clone https://github.com/Diyaneshwar-Pugazhendhi/ai-chatbot.git
cd ai-chatbot

# Start the application via Docker Compose
docker-compose up -d

# Or run locally
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
# Set your ANTHROPIC_API_KEY environment variable
export ANTHROPIC_API_KEY=your_key_here
python app.py
```

## 🔧 API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/api/query` | `POST` | Send a query to the AI bot and get a response |
| `/health` | `GET` | Health check endpoint |

### Example Request

```bash
curl -X POST http://localhost:8000/api/query \
  -H "Content-Type: application/json" \
  -d '{"query": "What is the capital of France?"}'
```

### Example Response

```json
{
  "response": "Processing: What is the capital of France?",
  "timestamp": "2026-08-30T23:45:12.123456",
  "model": "Claude API"
}
```

## 📁 Project Structure

```
ai-chatbot/
├── app.py              # Main Flask application
├── requirements.txt    # Python dependencies
├── Dockerfile          # Docker configuration
├── docker-compose.yml  # Docker Compose configuration
├── .dockerignore     # Docker ignore rules
├── .gitignore        # Git ignore rules
├── CHANGELOG.md      # Change log
└── README.md         # This file
```

## 🐳 Docker Deployment

The easiest way to run this project is via Docker Compose:

```bash
docker-compose up -d
```

This will start the AI chatbot container on port 8000. Access the API at `http://localhost:8000`.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit pull requests, create issues, or suggest features.

---

*Built with ❤️ using Anthropic Claude API*