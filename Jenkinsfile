pipeline {
    agent any
    stages {
        stage('Stop') {
            steps {
                bat 'pm2 delete helpdesk 2> errors.log' 
            }
        }
        stage('Install') {
            steps {
                bat "npm install"
            }
        }
        stage('Build') {
            steps {
                bat "npm run build"
            }
        }
        stage('Serve') {
            steps {
                bat "pm2 serve ./build 3000 --name helpdesk"
            }
        }
    }
}