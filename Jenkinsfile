pipeline {
    agent any

    tools {nodejs "node"}

    stages {
        stage('Test') {
            steps {
                sh 'npm install'
                sh 'npm test'
                success {
                    writeFile(file: 'resultJenkins.txt', text: 'All tests passed! <3')
                }
                failure {
                    writeFile(file: 'resultJenkins.txt', text: 'Not all tests passed! :(')
                }
            }
        }
    }
}
