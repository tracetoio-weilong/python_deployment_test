pipeline {
  agent any
  stages {
    stage('Start') {
      steps {
        sh  '''#bin/bash

              whoami
              printenv
            '''
      }
    }
    stage('create dev task') {
      when {
        branch 'feature/*'
      }
      steps {
        sh '''#!/bin/bash
              echo $jenkinsPythonTest
              jenkinsPythonTest="test10;$jenkinsPythonTest"
           '''
        println "${env.jenkinsPythonTest}"
        println "${jenkinsPythonTest}"

      }
    }
  }
}