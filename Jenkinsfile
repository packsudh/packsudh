pipeline {
  agent any
  stages {
    stage('Dev Build') {
      steps {
        echo 'Unit test executed'
      }
    }

    stage('Deploy to QA Env') {
      steps {
        echo 'Deploy to QA Env'
        echo 'Notify QA by email'
      }
    }

    stage('UI Testing(Smoke)') {
      parallel {
        stage('UI Testing(Smoke)') {
          steps {
            echo 'Selenium UI Tests'
            echo 'Run API Assured Test'
          }
        }

        stage('API Tests') {
          steps {
            echo 'Run API Tests'
          }
        }

        stage('Performance Tests') {
          steps {
            echo 'Run Jmeter Tests'
          }
        }

      }
    }

    stage('Deploy to UAT') {
      steps {
        echo 'Deploy to UAT'
      }
    }

    stage('Notify UAT Users') {
      steps {
        echo 'Notify UAT Users'
      }
    }

    stage('Certify UAT') {
      steps {
        echo 'Manually Certify'
        input 'Do you want to certify ?'
      }
    }

    stage('Prod Deploy') {
      steps {
        echo 'Deploy To Prod'
      }
    }

  }
}