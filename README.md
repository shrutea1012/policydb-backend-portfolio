# policydb-backend-portfolio
Backend development portfolio for an AI-powered university policy chatbot built with Python, FastAPI, Docker and Qdrant.
# PolicyDB — AI-Powered University Policy Chatbot

**Role:** Backend Developer (team capstone project)  
**Institution:** La Trobe University  
**Repository:** https://github.com/mindmeshgroup/policy-chatbot

## Overview

PolicyDB is a team-developed university policy question-answering system designed to help users find relevant information from university policy documents. The project uses a retrieval-augmented generation (RAG) architecture, combining document retrieval with an AI answer-generation component.

My primary responsibility was developing, testing and maintaining the **FastAPI backend** that receives questions, coordinates with other components and returns structured API responses.

## My Contributions

- Developed and maintained the `/ask` REST endpoint using **Python, FastAPI and Pydantic**.
- Implemented request validation, role handling, structured JSON responses, error handling and fallback behaviour.
- Added **rate limiting** to protect the API from excessive requests.
- Implemented **JSONL request logging** and response-time measurements to support debugging and monitoring.
- Supported integration with the retrieval and generation components, collaborating with teammates responsible for those services.
- Tested API behaviour through **Swagger UI**, including successful requests and troubleshooting integration errors.
- Contributed to backend technical documentation and sprint coordination.

## Technologies

| Area | Tools and technologies |
| --- | --- |
| Backend API | Python, FastAPI, Uvicorn, Pydantic |
| API protection and diagnostics | slowapi, validation, JSONL logging, timing metrics |
| Retrieval integration | Qdrant vector database; retrieval and reranking components developed collaboratively |
| AI integration | Ollama-based generation workflow, developed collaboratively |
| Infrastructure | Docker, Docker Compose |
| Testing and documentation | Swagger UI, API tests, technical documentation |

## System Architecture

PolicyDB uses a backend API to handle questions about university policies.

The backend was built using Python and FastAPI. When a user submits a question through the `/ask` endpoint, the backend processes the request and communicates with the retrieval component to find relevant information from policy documents stored in Qdrant.

The retrieved information is then used to produce a response with supporting citations.

The backend also handles input validation, error handling, rate limiting and request logging.

**Main components:**
- **FastAPI:** Handles incoming questions and API responses.
- **Qdrant:** Stores and retrieves relevant policy information.
- **Retrieval pipeline:** Finds and ranks relevant document chunks.
- **Generation component:** Produces answers using the retrieved information.
- **Docker:** Runs the Qdrant database locally.
- **Swagger UI:** Used to test API endpoints during development.

## Demonstration

I tested the backend locally using FastAPI's interactive Swagger documentation at `http://127.0.0.1:8000/docs`.

In a recent local test, the `/ask` endpoint accepted a university-policy question and returned **HTTP 200** with a structured JSON response containing an answer and supporting policy citations. I also confirmed that the Qdrant container was running in Docker.

Suggested evidence to include (after reviewing screenshots for private information):

1. Swagger UI showing the `/ask` request and response.
2. Terminal showing the running FastAPI service and request diagnostics.
3. Docker showing the running Qdrant service.

> **Note:** Local execution depends on the required Python packages, model availability and retrieval services. Some optional model integrations may produce errors if the configured Ollama model is not installed; a successful HTTP response alone does not prove every model component executed.

## Technical Challenges and Learning

Working on PolicyDB gave me practical experience diagnosing API integration issues, validating service responses, inspecting logs, handling missing dependencies and improving backend stability. I learned to separate problems in the API layer from problems in retrieval or model services and to document limitations clearly.

These experiences are relevant to junior systems administration, IT support, infrastructure troubleshooting and AI-enabled workflow implementation.

## Project Attribution

PolicyDB was developed as a **team capstone project**. This portfolio focuses on my individual backend contributions. Other team members worked on retrieval, generation, frontend and quality assurance.

**Full team repository:** https://github.com/mindmeshgroup/policy-chatbot
