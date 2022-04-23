pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker-compose --file dockerArtifacts/docker-compose.yml build'
            }
        }

        stage('Test') {
            steps {
                sh 'docker-compose --file dockerArtifacts/docker-compose.yml up'
            }
        }
    }
}
