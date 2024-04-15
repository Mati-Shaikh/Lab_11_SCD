pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                sh 'echo Checkout passed'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

       

        stage('Build Docker Image') {
            steps {
                sh 'echo docker build -t myapp:latest .'
            }
        }

        stage('Run Docker Image') {
            steps {
                sh 'echo docker run -d -p 80:80 myapp:latest'
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'echo docker push UmairAhmed/Lab11:latest'
                }
            }
        }
    }

