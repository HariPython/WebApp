pipeline {
  agent any
  stages {
    stage('Dev Code Pull') {
      steps {
        echo 'Pulling the code'
      }
    }

    stage('Build Maven Project') {
      steps {
        echo 'Build Maven Project'
      }
    }

    stage('Deploy to QA') {
      steps {
        echo 'Deploying to QA'
      }
    }

    stage('QA UI Test') {
      parallel {
        stage('QA UI Test') {
          steps {
            echo 'Testing UI'
          }
        }

        stage('QA API test') {
          steps {
            echo 'Testing API'
          }
        }

      }
    }

    stage('Certify QA') {
      steps {
        input 'Do you want to certify ?'
      }
    }

    stage('Deploy UAT') {
      steps {
        when() {
          branch 'dev'
          echo 'Deploying to UAT'
        }

      }
    }

    stage('Certify UAT') {
      steps {
        input 'Do you want to certify ?'
      }
    }

  }
}