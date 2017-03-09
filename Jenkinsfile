pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        node(label: 'build')
      }
    }
    stage('analysis') {
      steps {
        node(label: 'build')
      }
    }
    stage('acceptance') {
      steps {
        parallel(
          "Chrome": {
            node(label: 'build')
            
          },
          "edge": {
            node(label: 'build')
            
          },
          "firefox": {
            node(label: 'build')
            
          }
        )
      }
    }
    stage('staging') {
      steps {
        node(label: 'build')
      }
    }
    stage('Manual') {
      steps {
        input 'Continue ?'
      }
    }
    stage('Deploy') {
      steps {
        node(label: 'build')
      }
    }
  }
}
