node {
   stage('Checkout') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/jglick/simple-maven-project-with-tests.git'
   }
   stage('Build') {
      // Run the maven build
      sh "mvn clean package surefire-report:report"
   }
   stage('Publish') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
   stage('Deploy') {
      echo 'Deployed successfuly'
   }
}
