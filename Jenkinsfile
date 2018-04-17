pipeline {
  agent {
    docker {
      image 'maven:3.5.2-jdk-9'
    }
    
  }
  stages {
    stage('say-hello') {
      steps {
        echo 'Hello, world!'
        sh 'java -version'
        sh 'mvn -v'
      }
    }
  }
  environment {
    MY_NAME = '"Greg"'
  }
}