pipeline {
  agent {
    docker {
      image 'maven:3.5.2-jdk-9'
    }
    
  }
  stages {
    stage('say-hello') {
      steps {
        echo "Hello, ${MY_NAME}!"
        sh 'java -version'
        sh 'mvn -v'
        echo "${TEST_USER_USR}"
        echo "${TEST_USER_PSW}"
      }
    }
  }
  environment {
    MY_NAME = 'Greg'
    TEST_USER = credentials('test-user')
  }
}