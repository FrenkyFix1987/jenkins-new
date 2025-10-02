pipeline {
  agent any
  stages {
    stage('Hello') {
      parallel {
        stage('Hello') {
          agent any
          environment {
            TEST = '123'
          }
          steps {
            sh 'echo "Test"'
          }
        }

        stage('') {
          steps {
            sh 'echo "Parallel"'
          }
        }

      }
    }

    stage('World') {
      steps {
        sleep 5
        echo 'Hello World'
        sh 'exit 0'
      }
    }

  }
  post {
    always {
      echo 'Done'
    }

    failure {
      echo 'Failed!'
    }

  }
  parameters {
    string(name: 'USERID', defaultValue: '', description: 'Enter your user ID')
  }
  triggers {
    cron('H 9 * * 1-5')
    pollSCM('H/30 * * * *')
  }
}