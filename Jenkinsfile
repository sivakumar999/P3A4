pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    try {
                        // Checkout the source code from the Git repository
                        checkout scm
                    } catch (err) {
                        // Handle error
                        error "Failed to checkout source code: ${err}"
                    }
                }
            }
        }
        stage('Build') {
            steps {
                script {
                    try {
                        // Build the .NET Core Web API project
                        bat 'dotnet build Assign4.csproj'
                    } catch (err) {
                        // Handle error
                        error "Failed to build the project: ${err}"
                    }
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    try {
                        // Run unit tests
                        bat 'dotnet test Assign4.Tests.csproj'
                    } catch (err) {
                        // Handle error
                        error "Failed to run tests: ${err}"
                    }
                }
            }
        }
        stage('Publish') {
            steps {
                script {
                    try {
                        // Publish the Web API project
                        bat 'dotnet publish Assign4.csproj -c Release -o .\\publish'
                    } catch (err) {
                        // Handle error
                        error "Failed to publish the project: ${err}"
                    }
                }
            }
        }
    }
}
