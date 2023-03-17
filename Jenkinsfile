pipeline {
  agent any
  stages {
    stage('Checkout') {
      steps {
        echo 'Jenkins Pipeline'
        checkout scm
        sh '''curl -sL https://deb.nodesource.com/setup_16.x | sudo -E bash -
'''
        sh '''sudo apt-get install -y nodejs
'''
      }
    }

    stage('Client Tests') {
      steps {
        dir(path: 'client') {
          sh 'npm install'
          sh 'npm test'
        }

      }
    }

  }
}