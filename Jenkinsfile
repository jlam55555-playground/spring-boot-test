pipeline {
    agent {
        dockerfile {
            label 'sbt'
            args '-p 5000:8080'
        }
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}