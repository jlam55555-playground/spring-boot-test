pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh './gradlew build'
            }
        }
        stage('Cleanup') {
            steps {
                echo 'Cleaning up old docker containers...'
                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                    sh 'docker stop $(docker ps -a -q)'
                    sh 'docker rm $(docker ps -a -q)'
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'docker build -t sbt -f Dockerfile .'
                sh 'docker run -p 5000:8080 -d sbt'
            }
        }
    }
}