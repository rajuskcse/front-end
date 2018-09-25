pipeline {
    agent any
 
    stages {
        stage('Build') {
            steps {
                echo 'Building dependencies...'
                nodejs(nodeJSInstallationName: 'nodejs', configId: 'node 4.8.6') {
                    sh 'npm config ls'
                }
            }
        }
    }
}
