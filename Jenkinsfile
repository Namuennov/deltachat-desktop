pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                nodejs(nodeJSInstallationName: 'NodeJS') {
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
}
