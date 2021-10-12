def flag = false;

pipeline {
  agent any
  stages {
    // stage('Checkout'){
    //   steps {
    //     git branch: 'master',
    //         credentialsId: "${env.CREDENTIALS}",
    //         url: 'https://github.com/KevinECE/tclrepo.git'
    //   }
    // }
    stage('1 - Always run') {
      steps {
        echo 'Running'
      }
    }

    stage('2 - Run if hello.py changed') {
      when { changeset pattern: "/hello.py/", comparator: "REGEXP"}
      steps { 
        echo 'hello.py changed!'
        sh 'ls'
	      sh 'python hello.py' 
        script{ flag = true }
      }
    }

    stage('3 Run if hello.py ran') {
      when { expression { flag == true } }
      steps {
        echo 'hello.py ran! Now run goodbye.py'
        sh 'ls'
        sh 'python goodbye.py'
      }
    }
  }
}
