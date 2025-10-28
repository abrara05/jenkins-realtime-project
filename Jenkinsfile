pipeline {
  agent { label 'jenkins-agent' }
  tools {
    jdk 'Java17'
    maven 'Maven3'
  }
  stages{
    stage('Cleanup Workspace') {
      steps {
        cleanWs()
      }
    }
    stage('checkout from SCM'){
      steps{
        git branch: 'main' , credentialsId: 'github' , url: 'https://github.com/abrara05/jenkins-realtime-project'
      }
    }
    stage('Build Application'){
      steps {
        sh "mvn clean package"
      }
    }
    stage('Test Application') {
      steps {
        sh "mvn test"
      }
    }
  }
}
    
    
  
