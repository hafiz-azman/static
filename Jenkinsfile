pipeline {
  agent any
  stages {
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