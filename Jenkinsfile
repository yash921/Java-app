pipeline{
  agent { 
            label 'docker-xlarge'
        }
  
  stages {
    stage('Docker push') {
      steps {
        withDockerRegistry([credentialsId: 'docke', url: '']) {
            script {
            sh 'docker push yash922/testwebapp:3.0.0'
            }
        }
      }
    }
  }
}
