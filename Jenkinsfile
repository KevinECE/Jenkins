pipeline {
  agent any
  stages {
    stage('Checkout'){
      steps {
        git branch: 'master',
            credentialsId: "7b0c882b-e8f0-44bb-b1b2-cb4a214a5619",
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
