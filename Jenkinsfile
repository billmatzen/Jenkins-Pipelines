pipeline {
  agent {
    node {
      label 'BVTController01'
    }
    
  }
  stages {
    stage('Stage 1') {
      steps {
        parallel(
          "Stage 1 A": {
            sh 'ipconfig'
            
          },
          "Stage 1 B": {
            echo 'Hello, world!'
            
          }
        )
      }
    }
    stage('Stage 2') {
      steps {
        parallel(
          "Stage 1 B": {
            build(job: 'VerifyAutomationScripts', wait: true)
            
          },
          "Stage 2 B": {
            build 'SOAPStressTest'
            
          }
        )
      }
    }
    stage('Stage 3') {
      steps {
        sleep 30
      }
    }
  }
}