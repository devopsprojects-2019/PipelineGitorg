node {
   
   stage('Code Checkout') { 
     git credentialsId: 'githubID', url: 'https://github.com/itrainbatman/maven-examples.git'
     
    }
   stage('Build') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
      sh 'mvn clean compile'
      }
    }
   stage('Unit Test run') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
     sh 'mvn test'
      } 
    }
   stage('Sonar CodeAnalysis') {
     withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
        sh 'mvn sonar:sonar -Dsonar.projectKey=maven_apps -Dsonar.organization=itrainbatman -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=0767bb0a33926d7ea765c0ef95c6f8d67cdd5987'
      }  
    }
   stage('Package to Jfrog') {
    withMaven(jdk: 'JDK-1.8', maven: 'Maven-3.6.1') {
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
