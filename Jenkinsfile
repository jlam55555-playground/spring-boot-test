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
            steps {
                echo 'Deploying...'
                ansiblePlaybook {
                    playbook 'ansible-docker.yaml'
                }
            }
        }
    }
}