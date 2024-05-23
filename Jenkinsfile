pipeline {
    agent any
    triggers {
        pollSCM('*/1 * * * *')
    }
    stages {
        stage('build-docker-image') {
            steps {
                build_docker_image()
            }
        }
    }
}

def build_docker_image(){
    echo "Building docker image"
    sh "docker build --no-cache -t kkello/api-tests:latest ."

    echo "Pushing docker image"
    sh "docker push kkello/api-tests:latest"
}