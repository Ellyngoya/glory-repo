pipeline {
  agent any
  tools {
   maven 'M2_HOME'
  }
  stages {
    stage('Build'){
      steps {
        sh 'mvn clean'
        sh 'mvn install'
        sh 'mvn package'
      }
    } 
    stage('Test'){
      steps {
        sh 'mvn test'
       }
     }
   stage('Deploy'){
      steps {
        sh deploy adapters:[tomcat8(credentialsId: 'TomcatID', path: '', url: 'http://10.0.0.237:8080/')], contextPath: null, war: ''
     } 
   }
  } 
}
