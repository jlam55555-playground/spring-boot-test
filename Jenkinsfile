pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Deploy') {
            agent {
                dockerfile {
                    args '-p 5000:8080 -t sbt'
                }
            }
            steps {
                echo 'Deploying...'
            }
        }
    }
}