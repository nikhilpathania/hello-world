node {
   def mvnHome
   stage('Build') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/jglick/simple-maven-project-with-tests.git'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.           
      mvnHome = tool 'M3'
      sh "'${mvnHome}/bin/mvn' clean compile"
   }
    stage('Unit Test') {
        sh "'${mvnHome}/bin/mvn' test"        
        junit '**/target/surefire-reports/TEST-*.xml'
   }
   stage('Publish') {
        sh "'${mvnHome}/bin/mvn' package"
        archive 'target/*.jar'
   }
}
