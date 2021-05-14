pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          sh 'echo "Building Stage"'
        }
      }
    }
  }
  stages('Test') {
    steps {
      script {
        sh 'echo "Testing Stage"' 
      }
    }
  }
}
