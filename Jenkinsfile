#!groovy
@Library("shared-library") _ 

pipeline {
  agent { label "Linux" }
  stages {
    stage ('Shared Library') {
      steps {
        helloWorld()
      }
    }
    stage ('Start') {
      steps {
        // send build started notifications
        // sendNotifications 'STARTED'
      }
    }
    stage ('Install') {
      steps {
        // install required bundles
        // sh 'bundle install'
      }
    }
    stage ('Build') {
      steps {
        // build
        // sh 'bundle exec rake build'
      }

      post {
        success {
          // Archive the built artifacts
          // archive includes: 'pkg/*.gem'
        }
      }
    }
    stage ('Test') {
      steps {
        // run tests with coverage
        sh 'ls -al'
      }
      post {
        success {
          // publish html
          publishHTML target: [
              allowMissing: false,
              alwaysLinkToLastBuild: false,
              keepAll: true,
              reportDir: 'coverage',
              reportFiles: 'index.html',
              reportName: 'RCov Report'
            ]
        }
      }
    }
  }
  post {
    always {
      sendNotifications currentBuild.result
    }
  }
}