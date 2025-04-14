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
                bat 'docker build -t myappp .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat 'docker rm -f myappp || exit 0'
                bat 'docker run -d -p 3000:3000 --name myappp myappp:latest'
            }
        }
    }
}
