node('Pipeline') {
    stage('Initialize') {
        echo 'Initializing...'
        def node = tool name: 'node 4.8.6', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
        env.PATH = "${node}/bin:${env.PATH}"
    }

    stage('Checkout..') {
        echo 'Getting source code...'
        checkout scm
    }

    stage('Build..') {
        echo 'Building dependencies...'
        sh 'npm install'
    }

    stage('Test') {
        echo 'Testing...'
        sh 'npm test'
    }

    stage('Package..') {
        echo 'Package...'
        sh 'npm run Package'
        archiveArtifacts artifacts: '**/distribution/*.zip', fingerprint: true
    }
}
