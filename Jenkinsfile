pipeline {
    agent any

    stages {
        stage('lint HTML') {
            steps {             
              sh 'tidy -q -e *.html'
            }
        }
         stage('AWS') {
        steps {           

          withAWS(region:'us-west-2',credentials:'aws') {
            s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'heemjenkins')
          }
        }
      }
    }
}