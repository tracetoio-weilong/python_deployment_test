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
              jenkinsPythonTest="$BRANCH_NAME;$jenkinsPythonTest"
              echo $jenkinsPythonTest
           '''
           script{
        println "${jenkinsPythonTest}";
        env.jenkinsPythonTest = "${BRANCH_NAME}"+";"+"${jenkinsPythonTest}";
        println "${jenkinsPythonTest}";
      }

      }
    }
  }
}