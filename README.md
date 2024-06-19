# Intelligent Review Builder with AI

## Overview

This project is a web application designed to help users write product reviews using AI. The application leverages OpenAI's language models to generate review criteria and review text based on user inputs.

## Machine Learning Inference

### Framework and Implementation
The application uses the LangChain framework to handle text-based ML tasks. Specifically, it performs Retrieval QA (Question Answering) tasks, where the "documents" are product descriptions and rated criteria. This setup allows the LLM (Large Language Model) to effectively differentiate between prompts and context, improving performance and speeding up processing by caching vectorized descriptions.

### Embedding User Input
User inputs are embedded using a model from HuggingFace's sentence-transformers library. This embedding model, defined as an environment variable, can be smaller than the inference model, as long as it is compatible with GPT4All. GPT4All is used to load the models for various tasks.

### Types of Language Models
The application uses two types of LLMs, each offering different speed and cost trade-offs:

- **Local LLMs**:
  - Publicly available GPT-type models loaded by GPT4All at no cost.
  - Inference speed varies based on model size and system specifications.
- **ChatGPT API**:
  - Provided by OpenAI and uses the latest ChatGPT models.
  - Paid service designed for high usage with fast inference times of a few seconds after embedding.

### Default Configuration
The default setup uses a local LLM for generating criteria (slower) and the ChatGPT API for generating reviews (faster).

## Deployment

### Local Deployment
The API is built with FastAPI and served via uvicorn. To run the application locally:

1. Copy `.env.sample` to `.env`.
2. Add a valid OpenAI key to the `.env` file.
3. Start the application using uvicorn.

### Application Frontend
The frontend is built with Streamlit and deployed to Streamlit cloud. It provides a user-friendly interface for inputting product descriptions and ratings, and viewing generated review criteria and reviews.

## Repository
The project repository can be found at: [review-builder-web](https://github.com/Shahab89/review_builder_web.git).

Feel free to clone the repository and explore the codebase to understand how the application works and how to customize it for your needs.
