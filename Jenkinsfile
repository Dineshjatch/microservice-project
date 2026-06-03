pipeline{
    agent any

    stages{
        stage("Checkout"){
            steps{
                checkout scm
            }
        }

        stage("Build Docker Image"){
            steps{
                sh 'docker build -t microservice:latest .'
            }
        }

        stage('Deploy to Kubernetes'){
            steps{
                sh 'kubectl apply -f k8s/deployment.yaml'
            }
        }
    }
}