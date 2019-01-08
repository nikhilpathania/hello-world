pipeline {
   agent none
   stages {
      stage('Build & TEst') {
         agent {
            node {
               label 'docker'
            }
            steps {
               sh 'mvn -Dmaven.test.failure.ignore clean package'
               stash(name: 'build-test-artifacts', includes: '**/target/surefire-reports/TEST-*.xml,target/*.jar')
            }
         }
      }
   }
}
