pipeline {
    agent any
    environment {
        CI = true
        ARTIFACTORY_ACCESS_TOKEN = credentials('artifactory-access-token')
        JFROG_PASSWORD = credentials('jfrog-password')
    }
    stages {
        stage('Checkout Git Repository') {
            steps {
                git branch: 'master', url: 'https://github.com/gyan1909/jenkins'
            }
        }
        stage('Build maven job') {
            steps {
                sh './mvnw install'
            }
        }
    }
}