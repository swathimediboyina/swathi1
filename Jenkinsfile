pipeline {
  agent any
  tools {
    maven 'Maven'
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat9(credentialsId: '73f0f8f3-b317-4a0f-8997-e213d656cc70', path: '', url: 'http://13.234.56.157:8081')], contextPath: '/pipeline', onFailure: false, war: 'webapp/target/*.war' 
        }
      }
    }
  }
}
