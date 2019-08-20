pipeline {
    agent any

    stages {
        stage('Build') {
            steps {             
                echo 'Testing..'
                echo pwd
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