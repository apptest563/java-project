pipeline {
  agent any
  
  options {
    buildDiscarder(logRotator(numToKeepStr: '3', artifactNumToKeepStr:'3'))
  }
  
  stages {
    stage ('build') {
      steps {
        sh 'ant -f build.xml -v'
      }
    }
  }
  
  post {
    always {
      archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
    }
  }
}
