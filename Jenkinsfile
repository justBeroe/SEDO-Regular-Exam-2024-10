pipeline {
    agent any
    
    stages {
        stage('Checkout Repository') {
            steps {
                checkout scm
            }
        }

        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build project') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run dotnet tests') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
