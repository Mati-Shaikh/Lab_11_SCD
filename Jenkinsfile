pipeline {
    agent any
    environment {
        DOCKER_IMAGE = 'username/mywebapp:latest'
    }
    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'your-credentials-id', url: 'https://github.com/Mati-Shaikh/Lab_11_SCD'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }
        stage('Run Docker Image') {
            steps {
                sh 'docker run -d -p 80:80 $DOCKER_IMAGE'
            }
        }
        stage('Push Docker Image') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'docker-hub-credentials') {
                        sh 'docker push $DOCKER_IMAGE'
                    }
                }
            }
        }
    }
    post {
        always {
            sh 'echo "Pipeline execution is completed"'
        }
    }
}

