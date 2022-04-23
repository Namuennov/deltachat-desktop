pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'cd dockerArtifacts'
                sh 'docker-compose build'
            }
        }

        stage('Test') {
            steps {
                sh 'docker-compose up'
            }
        }
    }
}
