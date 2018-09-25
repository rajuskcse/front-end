pipeline {
    agent any
    
    tools {
      nodejs 'node 4.8.6'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                sh 'npm config set prefix /usr/local'
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'npm run test'
            }
        }
        stage('Package') {
            steps {
                echo 'Packaging....'
                sh 'npm run Package'
                archiveArtifacts artifacts: '**/distribution/*.zip', fingerprint: true
            }
        }
    }
}
