pipeline {
    agent{
        label 'docker'
    }
}

stages {
    stage('build stage from a docker image '){
        steps {}
        script{
            sh 'docker build -t ahmedkamal/docker-react -f Dockerfile.dev . '
         }
    }

    stage ('run test ') {
        steps {
            script {
                env.DOCKER_BUILDKIT=1
                sh'docker run -e CI=true ahmedkamal/docker-react npm run
            }
        }
    }

}