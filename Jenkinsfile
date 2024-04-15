pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the specified Git repository
                git url: 'https://github.com/Mati-Shaikh/Lab_11_SCD.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies using npm
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                // Build Docker image using Dockerfile in the project directory
                script {
                    docker.build('lab-11-scd:latest')  // Replace 'lab-11-scd' with your desired image name
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                // Run Docker container from the built image
                script {
                    docker.run('-p 3000:3000 --name lab-11-container lab-11-scd:latest')
                }
            }
        }

        stage('Push Docker Image (Optional)') {
            steps {
                // Push Docker image to Docker Hub (replace with your Docker registry)
                script {
                    docker.withRegistry('https://registry.example.com', 'docker-hub-credentials') {
                        docker.image('lab-11-scd:latest').push('latest')
                    }
                }
            }
        }
    }
}

