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
                echo '*** Image and Container con Docker...'
                bat 'docker build -t apoyo1 .'
                bat 'docker run -p 3001:3001 apoyo1'
                //bat 'npm start &'
            }
        }
    }
}
