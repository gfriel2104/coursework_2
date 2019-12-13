pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        node(label: server.js) {
          sh 'sh server.js'
        }

      }
    }

  }
}