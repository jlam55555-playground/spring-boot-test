pipeline {
    agent {
        dockerfile {
            args '-p 5000:8080 -t sbt'
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