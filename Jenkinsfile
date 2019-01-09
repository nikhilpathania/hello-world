pipeline {
  agent none
  stages {
    stage('Build') {
      agent {
        node {
          label 'docker'
        }

      }
      steps {
        sh 'mvn -Dmaven.test.failure.ignore clean package'
        stash(name: 'build-artifacts', includes: 'target/*.jar')
      }
    }
  }
}