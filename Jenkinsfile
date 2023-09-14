pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from your repository
                checkout git
            }
        }
        stage('Build') {
            steps {
                // Build the .NET Core Web API project
                sh 'dotnet build'
            }
        }
        stage('Test') {
            steps {
                // Run unit tests
                sh 'dotnet test'
            }
        }
        stage('Publish') {
            steps {
                // Publish the Web API project
                sh 'dotnet publish -c Release -o ./publish'
            }
        }
    }
    post {
        failure {
            // Add error handling and notifications here
            mail to: 'sivakumar59498gmail.com', subject: 'Pipeline Failed', body: 'The Jenkins pipeline failed.'
        }
    }
}
