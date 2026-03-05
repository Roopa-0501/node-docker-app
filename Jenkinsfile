pipeline {
    agent any

    stages {

        stage('Checkout from GitHub') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Roopa-0501/node-docker-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t node-docker-app:${BUILD_NUMBER} .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 3000:8080 node-docker-app:${BUILD_NUMBER}'
            }
        }

    }
}
