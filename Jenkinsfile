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
        sh 'mvn sonar:sonar -Dsonar.projectKey=com.project1 -Dsonar.organization=devaws2019 -Dsonar.host.url=https://sonarcloud.io -Dsonar.login=804b22d2f0ef236221e7b265ec65ea364988b776'
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
