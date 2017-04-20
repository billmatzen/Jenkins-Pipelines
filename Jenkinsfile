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
          "Stage 2": {
            build(job: 'VerifyAutomationScripts', wait: true)
            
          },
          "": {
            build 'SOAPStressTest'
            
          }
        )
      }
    }
    stage('') {
      steps {
        sleep 30
      }
    }
  }
}