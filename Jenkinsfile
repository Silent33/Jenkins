pipeline {
    agent {
        docker { image 'node:14-alpine' }
    }
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Silent33/Jenkins.git']]])
            }
        }
    }
}