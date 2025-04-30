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
      apt-get update
      apt-get install -y python3 python3-pip
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
