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
    stage('Upload to AWS') {
            steps {
              withAWS(region:'ap-southeast-2',credentials:'blueocean') {
                s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkins-pipeline3')
              }
            }
  }
}
}