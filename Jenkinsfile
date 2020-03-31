pipeline {
  agent any
  stages {
    stage('Lint HTML') {
      steps {
        sh 'tidy -q -e *.html'
      }
    }
    stage('Upload to AWS S3') {
      steps {
        sh 'ls -lah'
        sh '''
          echo "Multiline shell steps works too"
          ls -lah
        '''
        withAWS(credentials: 'aws-static', region: 'us-east-2') {
          s3Upload(file:'index.html', bucket:'hafiz-static', path:'index.html')
        }
      }
    }
  }
}