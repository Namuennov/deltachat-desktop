pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                nodejs(nodeJSInstallationName: 'NodeJS') {
                    sh 'npm install'
                    sh 'npm run build'
                    success {
                        writeFile(file: 'resultJenkins.txt', text: 'Built succesfully! <3')
                    }
                    failure {
                        writeFile(file: 'resultJenkins.txt', text: 'Build failed! :(')
                    }
                }
            }
        }

        stage('Test') {
            steps {
                nodejs(nodeJSInstallationName: 'NodeJS') {
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
