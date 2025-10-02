pipeline {
  agent any
  stages {
    stage('Hello') {
      agent any
      environment {
        TEST = '123'
      }
      steps {
        sh 'echo "Hello"'
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