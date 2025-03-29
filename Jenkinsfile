pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
              git branch: 'main', url: 'https://github.com/toteve/repo3_CI.git'
            }
        }

        stage('Build') {
            steps {
              echo '*** Building the project...'
              bat 'npm install'
            }
        }

        stage('Test') {
            steps {
              echo '*** Running tests...'
              bat 'npm run test'
            }
        }

        stage('Deploy') {
            steps {
                echo '*** Deploying the application...'
                bat 'npm start &'
            }
        }
    }
}
