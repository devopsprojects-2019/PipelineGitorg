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
   stage('Sonar CodeAnalysis') {
     withMaven(jdk: 'jdk-1.8', maven: 'maven-3.6') {
        sh 'mvn sonar:sonar -Dsonar.projectKey=devopsprojects-2019_PipelineGitorg -Dsonar.organization=devopsprojects-2019 -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=75224bc8a83ba8d8e13a69041cd38be097da9a83'
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
