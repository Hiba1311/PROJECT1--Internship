
PROJECT : CI/CD Pipeline with GitHub Actions and Docker - Node.js App

Overview:
This project demonstrates how to set up a Continuous Integration and Continuous Deployment (CI/CD) pipeline using GitHub Actions for a Node.js application. The app is containerized with Docker and pushed to Docker Hub on every push to the main branch.

Objective: 
Set up a full CI/CD pipeline that builds a Docker image, runs tests, and deploys locally. 

Tools:
 GitHub Actions, Docker, Docker Hub (free), Minikube or local VM 

Steps Covered:

1. Project Setup:
•	Initialized Node.js app using npm init -y
•	Installed Express: npm install express
•	Created index.js with a basic Express server.
•	Created a dummy test file app.test.js using Jest.
•	Installed Jest for testing: npm install --save-dev jest
•	Updated `package.json` to include:
                                "scripts": {
                                    "start": "node index.js",
                                     "test": "jest"
                                     }

2. Docker Setup:
•	Created a Dockerfile to build a Node.js Docker image.
•	(Optional) Added ‘docker-compose.yml’ to define service ports.

3. GitHub Actions Setup:
 Created .github/workflows/main.yml to define CI/CD workflow.
 The workflow:
•	Checks out code from the repo.
•	Sets up Node.js environment.
•	Installs dependencies.
•	Runs tests using Jest.
•	Builds Docker image and tags it as `hiba175/ci-cd-demo`.
•	Pushes the image to Docker Hub.

4. Secrets Management:
•	Added Docker Hub credentials to GitHub Secrets:
•	DOCKER_USERNAME: Docker Hub username.
•	DOCKER_PASSWORD: Docker Hub password.

5. GitHub Actions Execution:
•	The pipeline runs automatically on each push or pull request to the main branch.
•	Verifies tests, builds the image, and pushes it to Docker Hub.

Outcome:
Whenever you push code to the main branch, your app is automatically tested, packaged into a Docker image, and deployed to Docker Hub under `hiba175/ci-cd-demo`.

Docker image link : https://hub.docker.com/repository/docker/hiba175/ci-cd-demo/general

Note:
We don’t need to enter credentials manually in your terminal. GitHub Actions uses the secrets securely.
