pipeline {
  agent any
  stages {
    stage('Start') {
      steps {
        sh  '''#bin/bash

              whoami
            '''
      }
    }
    stage('create dev task') {
      when {
        branch 'feature/*'
      }
      steps {
        sh '''#!/bin/bash
              FILE=/tmp/jenkinsPythonTest
              if [ -f $FILE ]; then
                 branches=$(cat $FILE)
              else
                 branches=
              fi

              echo "$BRANCH_NAME  ===> $branches"

              if [[ $list =~ (^|;)"$item"($|;) ]] ; then
                echo "Existing branch"
              else
                echo "New branch"
                branches="$BRANCH_NAME;$branches"
                echo $branches
                echo $branches > $FILE
                echo "deployment starts"
              fi
              
           '''
      }
    }
  }
}