pipeline {
    agent any

    environment {
        APP_NAME = "myapp"
        DOCKER_IMAGE = "myapp:latest"
        CONTAINER_NAME = "myapp-container"
    }

    stages {
        stage('Pull Code') {
            steps {
                echo 'Pulling code from GitHub...'
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                sh "docker build -t ${DOCKER_IMAGE} ."
            }
        }

        stage('Stop Old Container') {
            steps {
                echo 'Stopping old container if running...'
                sh """
                if [ \$(docker ps -q -f name=${CONTAINER_NAME}) ]; then
                    docker stop ${CONTAINER_NAME}
                    docker rm ${CONTAINER_NAME}
                fi
                """
            }
        }

        stage('Deploy Container') {
            steps {
                echo 'Deploying new container...'
                sh "docker run -d --name ${CONTAINER_NAME} -p 8080:8080 ${DOCKER_IMAGE}"
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
