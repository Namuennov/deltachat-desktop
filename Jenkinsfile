pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker-compose --file dockerArtifacts/docker-compose.yml build'
                script {
                    if (currentBuild.currentResult == 'SUCCESS') {
                        mail bcc: '', body: "Built succesfully! <3", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "Jenkins deltachat: build status", to: "jakubforys@student.agh.edu.pl";
                    }
                    else {
                        mail bcc: '', body: "Build failed! :(", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "Jenkins deltachat: build status", to: "jakubforys@student.agh.edu.pl";
                    }
                }
            }
        }

        stage('Test') {
            steps {
                sh 'docker-compose --file dockerArtifacts/docker-compose.yml up'
                script {
                    if (currentBuild.currentResult == 'SUCCESS') {
                        mail bcc: '', body: "All tests passed! <3", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "Jenkins deltachat: tests status", to: "jakubforys@student.agh.edu.pl";
                    }
                    else {
                        mail bcc: '', body: "Some tests failed! :(", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "Jenkins deltachat: tests status", to: "jakubforys@student.agh.edu.pl";
                    }
                }
            }
        }
    }
}
