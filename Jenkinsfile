pipeline {
    agent any

    stages {
        stage('Checkout the repository') {
            steps {
                checkout scm
            }
        }

        stage('Build the project') {
            steps {
                bat 'dotnet build'
            }
        }

        stage('Restore the project') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Run Test') {
            steps {
                bat 'dotnet test'
            }
        }
    }
    post {
        always {
            echo 'Pipeline completed'
        }
        success {
            echo 'Build succeeded'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}