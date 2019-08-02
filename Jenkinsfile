node {
   
   stage('Code Checkout') { 
     git credentialsId: 'githubID', url: 'https://github.com/devopsprojects-2019/PipelineGitorg.git'
     
    }
   stage('Build') {
    withMaven(jdk: 'jdk-1.8', maven: 'maven-3.6') {
      sh 'mvn clean compile'
      }
    }
   stage('Unit Test run') {
    withMaven(jdk: 'jdk-1.8', maven: 'maven-3.6') {
     sh 'mvn test'
      } 
    }
   
   stage('Sonarqube analysis'){
      def scannerHome = tool 'javascanner';
   withSonarQubeEnv(credentialsId: 'sonar_qube') {
    withMaven(jdk: 'jdk-1.8', maven: 'maven-3.6') {
    sh 'mvn sonar:sonar' 
      }
   }
   }
   stage('Package to Jfrog') {
    withMaven(jdk: 'jdk-1.8', maven: 'maven-3.6') {
     sh 'mvn package'
      }
    }
   
   stage('Deploy to Dev') {
     
    }
   stage('Automation Testing') {
     
    }
   stage('Deploy to Test') {
     
    }
   stage('Smoke Testing') {
     
    }
   stage('Deploy to Prod') {
     
    }
   stage('Acceptance Testing') {
     
    }
}
