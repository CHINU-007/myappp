pipeline {
    agent any

    environment {
        IMAGE_NAME = 'myappp'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/CHINU-007/myappp.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myappp .'
            }
        }

        stage('Run Docker Container') {
            steps {
                // Stop and remove any running container (ignore error if not running)
                sh 'docker rm -f myappp || true'
                // Run the container
                sh 'docker run -d -p 3000:3000 --name myappp myappp:latest'
            }
        }
    }
}
