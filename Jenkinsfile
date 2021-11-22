pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build demo-app'
        sh 'sh run_build_script.sh'
      }
    }

    stage('Linux Tests') {
      parallel {
        stage('Linux Tests') {
          steps {
            echo 'Run Linux tests'
            sh 'sh run_linux_tests.sh'
          }
        }

        stage('Windows Test stage') {
          steps {
            echo 'run windows test'
          }
        }

      }
    }

    stage('Deploy Stage') {
      steps {
        echo 'Deploy to staging environment'
        input 'OK to deploy into production'
      }
    }

    stage('Deploy a Production Stage') {
      steps {
        echo 'Deploy to Prod'
      }
    }

  }
}