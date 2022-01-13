pipeline{
  agent { 
            label 'docker-xlarge'
        }
  stages {
    stage('SCM checkout') {
      steps {
          git branch: 'master', url: 'https://github.com/yash921/Java-app.git'
        }
      }
      
    stage("MVN package") {
      steps {
        script {
          def mvnHome = tool name: 'maven', type: 'maven'
          def mvnCMD = "${mvnHome}/bin/mvn"
          sh "${mvnCMD} clean package"
        }
      }
    }

    stage('Docker Build and Tag') {
      steps {
          sh 'docker build -t yash922/testwebapp:2.0.0 .' 
        }
    }
  }
}
