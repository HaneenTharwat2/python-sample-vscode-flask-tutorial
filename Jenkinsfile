pipeline{
    agent any

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
