pipeline {
    agent {
        label 'docker'
    }

    stages {
        stage('Build stage from a Docker image') {
            steps {
                script {
                    sh 'docker build -t ahmedkamal/docker-react -f Dockerfile.dev .'
                }
            }
        }

        stage('Run tests') {
            steps {
                script {
                    env.DOCKER_BUILDKIT = "1"
                    sh 'docker run -e CI=true ahmedkamal/docker-react npm run test'
                }
            }
        }
    }
}
