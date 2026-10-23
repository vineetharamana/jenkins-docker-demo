
<img width="1366" height="697" alt="Screenshot from 2026-10-23 14-11-02" src="https://github.com/user-attachments/assets/87df215b-6b08-4545-92c8-d7672b3a7cba" />


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
# Jenkins Docker Pipeline

## Project Description
This project demonstrates how to automate application building and deployment using Jenkins and Docker.

## Tools Used
- Jenkins
- Docker
- Git and GitHub
- Node.js

## Project Structure
```text
jenkins-docker-project/
├── Jenkinsfile
├── Dockerfile
├── package.json
├── server.js
└── .dockerignore
```

## Pipeline Stages
1. **Checkout:** Download source code from GitHub.
2. **Build:** Build the Docker image.
3. **Test:** Check the application syntax.
4. **Deploy:** Run the application in a Docker container.
5. **Verify:** Check the application health endpoint.

## How to Run

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/jenkins-docker-project.git
cd jenkins-docker-project
```

Build the Docker image:

```bash
docker build -t jenkins-docker-app .
```

Run the container:

```bash
docker run -d --name jenkins-docker-app -p 3000:3000 jenkins-docker-app
```

Open the application:

http://localhost:3000

Health check:

http://localhost:3000/health

