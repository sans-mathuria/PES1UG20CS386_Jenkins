pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'g++ new.cpp -o new'
        echo 'Build Stage Successful'  
    }
  }
    stage('Test'){
    steps {
    sh './new'
    echo 'Test Stage Successful'
    post {
      always {
        junit 'target/surefire-reports/*.xml'
        }
      }
    }
  }
    stage ('Deploy') { 
      steps{
        sh 'mvn deploy'
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
