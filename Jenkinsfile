pipeline {
    agent any
 
    stages {
        stage('Build') {
            steps {
                echo 'Building dependencies...'
                nodejs(nodeJSInstallationName: 'node 4.8.6') {
                    sh 'npm config ls'
                }
            }
        }
    }
}
