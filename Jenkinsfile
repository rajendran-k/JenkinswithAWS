pipeline {
    agent any

    stages {
        stage('Build') {
            steps {             
                sh ‘tidy -q -e *.html’
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh ‘tidy -q -e *.html’
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                sh ‘tidy -q -e *.html’
            }
        }
    }
}