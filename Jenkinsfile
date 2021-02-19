pipeline {
  agent any
  stages {
    stage('Compile Stage') {
      steps {
        sh " echo $GIT_BRANCH is the current branch"
        sh ' echo compile'
        sh 'mvn compile'
        archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
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