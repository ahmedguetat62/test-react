pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('self monitoring') {
            steps {
                sh 'pwd'
                sh 'ls -alihs'
                sh 'node -v'
                sh "printenv | sort"
            }
        }
        stage('Build') {
            steps {
                sh 'npm i'
            }
        }
        stage('start'){
            steps {
                sh 'npm start'
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        
    }
    
    triggers {
        pollSCM('*/5 * * * *') // Vérifie les modifications du référentiel toutes les 5 minutes
    }
}
