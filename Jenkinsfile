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
        sh '''
            python3 -m venv venv
            . venv/bin/activate
            pip3 install -r requirements.txt
        '''
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
