pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout your code from Git repository
                git 'https://github.com/aditya-sridhar/simple-reactjs-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                // Build Docker image using Dockerfile in the project directory
                script {
                    docker.build('my-react-app:latest')  // Replace 'my-react-app' with your desired image name
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                // Run Docker container from the built image
                script {
                    docker.run('-p 3000:3000 --name my-container my-react-app:latest') // Replace 'my-react-app' with your image name
                }
            }
        }
    }
}
