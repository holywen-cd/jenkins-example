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
            sh ' sleep 20'
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
echo BUZZ_NAME $BUZZ_NAME
echo "uploading to dsnexus: https://mynexus.com/springboot.jar (50 M uploaded)"'''
          }
        }

      }
    }

    stage('Testing Stage') {
      steps {
        sh ' echo Testing'
      }
    }
    
    stage('Deploy approval'){
      input "Deploy to prod?"
    }
    
    stage('Deployment Stage') {
      steps {
        sh ' echo Deployment'
      }
    }

  }
}
