pipeline {
    agent any

    stages {
        stage('lint HTML') {
            steps {        
              sh 'echo "syntax checking"'     
              sh 'tidy -q -e *.html'
            }
        }
         stage('AWS') {
        steps {                  
            sh 'echo "sending data to aws"'
          withAWS(region:'us-west-2',credentials:'aws') {
            s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'heemjenkins')
          }
        }
      }
    }
}