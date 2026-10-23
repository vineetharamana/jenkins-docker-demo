
pipeline {
    agent any

    environment {
        IMAGE_NAME = 'jenkins-docker-demo'
        CONTAINER_NAME = 'jenkins-demo-app'
        APP_PORT = '3000'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Validate Application') {
            steps {
                sh 'node --check server.js'
                sh 'npm install --package-lock-only --ignore-scripts'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ${IMAGE_NAME}:${BUILD_NUMBER} .'
                sh 'docker tag ${IMAGE_NAME}:${BUILD_NUMBER} ${IMAGE_NAME}:latest'
            }
        }

        stage('Deploy Application') {
            steps {
                sh '''
                    docker rm -f ${CONTAINER_NAME} || true

                    docker run -d \
                      --name ${CONTAINER_NAME} \
                      --restart unless-stopped \
                      -p ${APP_PORT}:3000 \
                      ${IMAGE_NAME}:${BUILD_NUMBER}
                '''
            }
        }

        stage('Verify Deployment') {
            steps {
                sh '''
                    for i in $(seq 1 15); do
                      if curl -fsS http://localhost:${APP_PORT}/health; then
                        echo "Deployment successful"
                        exit 0
                      fi
                      sleep 2
                    done

                    echo "Application health check failed"
                    docker logs ${CONTAINER_NAME}
                    exit 1
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Check the console output.'
        }
    }
}

