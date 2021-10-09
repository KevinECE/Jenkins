pipeline {
  agent any
  stages {
    stage('Checkout'){
      steps {
        git branch: 'master',
            credentialsId: "${env.CREDENTIALS}",
            url: 'https://github.com/KevinECE/tclrepo.git'
      }
    }
    stage('Build') {
      steps { 
        sh 'ls'
	      sh 'python hello.py' 
      }
    }
  }
}
