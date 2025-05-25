node {
    def dockerImage

    stage('Checkout') {
        checkout scm
    }

    stage('Build Image') {
        dockerImage = docker.build("haneentharwat/sample-flask:${env.BUILD_NUMBER}")
    }

    stage('Push Image') {
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-creds') {
            dockerImage.push()
        }
    }

    stage('Done') {
        echo "✅ Image pushed: haneentharwat/sample-flask:${env.BUILD_NUMBER}"
    }
}

