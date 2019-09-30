pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'echo "Hello World here g"'
        sh '''
                          echo “Multiline shell steps works too”
                          ls -lah
                       '''
      }
    }
    stage('Lint HTML') {
          steps {
            sh 'tidy -q -e *.html'
          }
        }
  }
}