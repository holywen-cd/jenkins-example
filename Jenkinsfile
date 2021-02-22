pipeline {
  agent any
  stages {
    stage('Compile Stage') {
      parallel {
        failfast true
        stage('Compile Stage') {
          steps {
            sh " echo $GIT_BRANCH is the current branch"
            sh ' echo compile'
            sh 'mvn compile'
            archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
          }
        }

        stage('Parallel Stage') {
          steps {
            sh 'echo "abc"'
            node(label: '*') {
              sh 'echo agent'
            }

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
