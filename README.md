# LLM-FastAPI: Gemini-Powered Chatbot with React Frontend

This project provides a full-stack chatbot interface that allows users to interact with Google's Gemini large language model (LLM). It consists of a FastAPI backend and a ReactJS frontend, both containerized with Docker for easy deployment.

## Features

- **Chatbot UI**: A responsive web interface to communicate with the Gemini LLM.
- **Gemini API Integration**: Enter your Gemini API key and prompts to receive AI-generated responses.
- **Full-stack Solution**: Backend using FastAPI (Python) and frontend using ReactJS.
- **Containerized Deployment**: Easily build, run, and manage with Docker and Docker Compose.
- **CORS Enabled**: Cross-origin requests between frontend and backend are supported.

## Directory Structure

```
llm-fastapi/
├── backend/         # FastAPI backend for Gemini API interaction
│   ├── main.py      # Main API service
│   ├── requirements.txt
│   └── Dockerfile
├── frontend/        # ReactJS frontend client
│   ├── src/
│   │   ├── App.js   # Main chatbot UI logic
│   │   ├── App.css  # Styling for chatbot UI
│   │   └── ...
│   ├── public/
│   └── Dockerfile
├── start.sh         # Script to build and start containers
├── commands.txt     # Setup and operation command log
└── README.md        # Project documentation
```

## Getting Started

### Prerequisites

- [Docker](https://www.docker.com/get-started)
- [Node.js](https://nodejs.org/) (for local frontend development)
- [Python 3.10+](https://www.python.org/downloads/) (for local backend development)
- A valid Gemini API key

### Quick Start (Docker Compose)

1. **Clone the repository:**

   ```sh
   git clone https://github.com/atcode11/llm-fastapi.git
   cd llm-fastapi
   ```

2. **Run the startup script:**

   ```sh
   ./start.sh
   ```

   This will build and start both backend and frontend containers.

3. **Access the Chatbot:**
   
   - Frontend: [http://localhost:3000](http://localhost:3000)
   - Backend API: [http://localhost:8000](http://localhost:8000)

### Manual Run

#### Backend

1. Go to the `backend` directory:

   ```sh
   cd backend
   ```

2. Build and run the Docker container:

   ```sh
   docker build -t llm .
   docker run -p 8000:8000 llm
   ```

3. The API will be available at [http://localhost:8000](http://localhost:8000)

#### Frontend

1. Go to the `frontend` directory:

   ```sh
   cd frontend
   ```

2. Install dependencies and start the app:

   ```sh
   npm install
   npm start
   ```

3. The web interface will be at [http://localhost:3000](http://localhost:3000)

### Configuration

- The **backend** expects requests to `/get_gemini_completion` with a Gemini API key and a user prompt.
- The **frontend** requires configuration of the backend API URL (see `environment.js` in frontend).

## Usage

1. **Enter your Gemini API key** in the web UI.
2. **Type a prompt or question** in the chat input.
3. **Submit** and the Gemini LLM will respond in the interface.

## Main Components

### Backend (FastAPI)

- `main.py`: Provides endpoints for health check and LLM completion via Gemini.
- Handles POST requests for chat completion, configures Gemini client, and returns the generated response.

### Frontend (ReactJS)

- `App.js`: Handles user input, sends data to the backend, and displays chat responses.
- `App.css`: Styles the UI for an interactive chatbot experience.

### Docker

- Backend and frontend have separate Dockerfiles for easy containerization.
- Use `docker-compose.yml` for orchestrating both services.

## License

This project is licensed under the MIT License.

## Acknowledgments

- [FastAPI](https://fastapi.tiangolo.com/)
- [ReactJS](https://react.dev/)
- [Google Gemini LLM](https://ai.google.dev/)
