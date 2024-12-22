pipeline {
    agent any
    triggers {
        pollSCM('*/1 * * * *')
    }
    stages {
        stage('build-and-push-docker-image') {
            steps {
                buildAndPushDockerImage()
            }
        }
    }
}

def buildDockerImage() {
    echo "Building docker image..."
    sh "docker build -t sandraosadcuka/api-tests:latest ."

    echo "Pushing image to docker registry..."
    sh "docker push sandraosadcuka/api-tests"
}
