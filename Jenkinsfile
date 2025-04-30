pipeline {
  agent any
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
