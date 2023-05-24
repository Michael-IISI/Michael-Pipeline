#!groovy
@Library("shared-library") _ 

pipeline {
  agent any
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
        sh 'echo Start'
      }
    }
    stage ('Install') {
      steps {
        // install required bundles
        // sh 'bundle install'
        sh 'echo Install'
      }
    }
    stage ('Build') {
      steps {
        // build
        // sh 'bundle exec rake build'
        sh 'echo Build'
      }
    }
    stage ('Test') {
      steps {
        // run tests with coverage
        sh 'ls -al'
      }
    }
  }
}