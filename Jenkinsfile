pipeline {
  agent any
  stages {
    stage('Clone Repo') {
      steps {
        git 'https://github.com/CHINU-007/your-repo.git'
      }
    }
    stage('Build Docker Image') {
      steps {
        sh 'docker build -t myappp:latest .'
      }
    }
    stage('Run Container') {
      steps {
        sh 'docker stop myappp || true && docker rm myappp || true'
        sh 'docker run -d -p 3000:3000 --name myappp myappp:latest'
      }
    }
  }
}
