node {
   def mvnHome
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/jglick/simple-maven-project-with-tests.git'
    
   }
   stage('Build') {
       sh ‘docker run -i --rm --name my-maven-project -v “$PWD”:/usr/src/mymaven -w /usr/src/mymaven maven:3-jdk-8 mvn install’
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
}
