pipeline {
    agent any

    stages {
        stage('Restore dependencies') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                echo 'Restoring dependencies...'
                bat 'dotnet restore'
            }
        }
        stage('Build project') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                echo 'Building the project...'
                bat 'dotnet build --no-restore'
            }
        }
        stage('Execute tests') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                echo 'Executing tests...'
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
