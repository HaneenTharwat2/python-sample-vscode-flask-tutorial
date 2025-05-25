pipeline{
    agent anynode {
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


    stages{
        stage("build Docker image"){
            steps{
                sh "docker build -t haneentharwat/data-iti:v${BUILD_NUMBER} ."
            }
        }
        stage("Push Docker image"){
            steps{
                sh "docker push haneentharwat/data-iti:v${BUILD_NUMBER}"
            }
        }
    }
}
