pipeline {
    agent any
 
    stages {
        stage('Build..') {
            steps {
                echo 'Building dependencies...'
                nodejs(nodeJSInstallationName: 'node 4.8.6') {
                    sh 'npm install'
                }
            }
        }
        stage('Test..') {
            steps {
                echo 'Testing...'
                nodejs(nodeJSInstallationName: 'node 4.8.6') {
                    sh 'npm run test'
                }
            }
        }
        stage('Package..') {
            steps {
                echo 'Building Package...'
                nodejs(nodeJSInstallationName: 'node 4.8.6') {
                    sh 'npm run package'
                    archiveArtifacts artifacts: '**/distribution/*.zip', fingerprint: true
                }
            }
        }
    }
}
