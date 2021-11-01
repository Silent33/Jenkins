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
        stage('Install and build') {
            steps {
                sh """
                yarn install
                yarn build
                rm -rf node_modules
                """
            }
        }
        stage('Deploy') {
            steps {
                sh """
                create-react-app react-gh-pages
                yarn deploy
                """
            }
        }
    }
}