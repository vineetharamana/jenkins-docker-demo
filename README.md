===> Jenkins Docker Pipeline

## Project Description
This project demonstrates how to automate application building and deployment using Jenkins and Docker.

## Tools Used
- Jenkins
- Docker
- Git and GitHub
- Node.js

## Project Structure
jenkins-docker-project/
├── Jenkinsfile
├── Dockerfile
├── package.json
├── server.js
└── .dockerignore

## How to Run

Clone the repository:
git clone https://github.com/vineetharamana/jenkins-docker-project.git
cd jenkins-docker-project

Build the Docker image:

docker build -t jenkins-docker-app .

Run the container:
docker run -d --name jenkins-docker-app -p 3000:3000 jenkins-docker-ap

Open the application:

http://localhost:3000

Health check:

http://localhost:3000/health

## Jenkins Setup
1. Create a Pipeline job in Jenkins.
2. Configure the GitHub repository URL.
3. Select **Pipeline script from SCM**.
4. Choose Git and set the script path to `Jenkinsfile`.
5. Click **Build Now** to run the pipeline.

