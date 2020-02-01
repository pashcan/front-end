pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                nodejs(nodeJSInstallationName: 'NodeJS 4.8.6') {
                    sh 'npm install'
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                nodejs(nodeJSInstallationName: 'NodeJS 4.8.6') {
                    sh 'npm install'
                    sh 'npm run test'
                }
            }
        }
        stage('Package') {
            steps {
                echo 'Packaging....'
                nodejs(nodeJSInstallationName: 'NodeJS 4.8.6') {
                    sh 'npm install'
                    sh 'npm run package'
                }
                archiveArtifacts artifacts: '**/distribution/*.zip', fingerprint: true 
            }
        }
    }
}