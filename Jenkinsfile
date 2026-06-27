pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {
        stage('Restore') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet restore Homies.sln'
            }
        }

        stage('Build') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet build Homies.sln --no-restore'
            }
        }

        stage('Test') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet test Homies.sln --no-build --verbosity normal'
            }
        }
    }
}