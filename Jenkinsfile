pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'gcc new.cpp -lstdc++'
        echo 'Build Stage Successful'  
    }
  }
    stage('Test'){
    steps {
    sh './a.out'
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