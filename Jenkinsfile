pipeline {
  agent any
  stages {
    stage('Compile Stage') {
      failFast true
      parallel {
        stage('Compile Stage') {
          steps {
            sh " echo $GIT_BRANCH is the current branch"
            sh ' echo compile'
            //sh 'mvn compile'
            //archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
          }
        }

        stage('Parallel Stage') {
          agent any
          environment {
            BUZZ_NAME = 'Holy'
          }
          steps {
            sh 'echo "abc"'
            sh '''echo agent
echo BUZZ_NAME $BUZZ_NAME'''
          }
        }

      }
    }

    stage('Testing Stage') {
      steps {
        sh ' echo Testing'
      }
    }

    stage('Deployment Stage') {
      steps {
        sh ' echo Deployment'
      }
    }

  }
}
