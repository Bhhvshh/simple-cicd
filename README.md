# simple-cicd

A simple Node.js/Express web application with a CI/CD pipeline using GitHub Actions and Docker.

## Overview

This project demonstrates a basic CI/CD workflow:
- A minimal Express server that responds with a greeting
- Automated testing, Docker image building, and deployment via GitHub Actions

## Prerequisites

- [Node.js](https://nodejs.org/) v18+
- [Docker](https://www.docker.com/) (optional, for containerized runs)

## Getting Started

### Install dependencies

```bash
npm install
```

### Run the server

```bash
npm start
```

The server will start on port `3000` by default. You can override this with the `PORT` environment variable:

```bash
PORT=8080 npm start
```

Visit `http://localhost:3000` to see the response.

## Running Tests

```bash
npm test
```

## Docker

### Build the image

```bash
docker build -t simple-cicd .
```

### Run the container

```bash
docker run -p 3000:3000 simple-cicd
```

## CI/CD Pipeline

The GitHub Actions workflow (`.github/workflows/ci.yml`) runs on every push or pull request to `main` and performs the following steps:

1. **Checkout** – checks out the repository
2. **Setup Node.js** – configures Node.js v18
3. **Install dependencies** – runs `npm install`
4. **Run tests** – runs `npm test`
5. **Build Docker image** – builds the Docker image to verify the `Dockerfile`
