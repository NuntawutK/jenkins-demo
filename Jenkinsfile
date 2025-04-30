pipeline {
  agent {
        docker {
            image 'python:3.9'
            args '-v /var/jenkins_home:/var/jenkins_home'
        }
    }
  stages {
    stage('Clone') {
      steps {
        checkout scm
      }
    }
    stage('Install Dependencies') {
      steps {
        sh 'pip install -r requirements.txt'
      }
    }
    stage('Run Tests') {
      steps {
        sh 'pytest'
      }
    }
    stage('Build Docker Image') {
      steps {
        sh 'docker build -t my-python-app .'
      }
    }
  }
}
