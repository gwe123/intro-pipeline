
library 'SharedLibs'
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
    stage('Deploy') {
      options {
        timeout(time: 1, unit: 'MINUTES')
      }
      input {
        message 'Should we continue?'
      }
      steps {
        echo 'Continuing with deployment'
      }
    }
    stage('Shared Lib') {
         steps {
             helloWorld("Jenkins")
         }
      }

  }

  environment {
    MY_NAME = 'Greg'
    TEST_USER = credentials('test-user')
  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}
