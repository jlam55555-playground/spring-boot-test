pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh './gradlew build'
            }
        }
        stage('Deploy') {
            agent {
                dockerfile {
                    additionalBuildArgs '-t sbt'
                    args '-p 5000:8080'
                }
            }
            steps {
                echo 'Deploying...'
            }
        }
    }
}