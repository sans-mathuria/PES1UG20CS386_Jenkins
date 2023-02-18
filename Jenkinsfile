pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        build job : "PES1UG20CS386_SanskritiMathuria-1", wait : true
        sh 'g++ new.cpp -o new'
        echo 'Build Stage Successful'  
    }
  }
    stage('Test'){
    steps {
      sh 'make new'
      echo 'Test Stage Successful'
     }
  }
    stage ('Deploy') { 
      steps{
        echo 'Deployment Successful'
      }
    }
  }
  post {
    failure {
    echo 'Pipeline failed'
    }
  }
}
