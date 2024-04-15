pipeline {
    agent any

    stages {
        stage('Checkout') {
           
            steps {
                git url: 'https://github.com/Mati-Shaikh/Lab_11_SCD.git'
            }
        }

        stage('Install Dependencies') {
          
            steps {
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
        
            steps {
                script {
                    docker.build('lab-11-scd:latest') 
                }
            }
        }

        stage('Run Docker Container') {
           
            steps {
                script {
                    docker.run('-p 3000:3000 --name lab-11-container lab-11-scd:latest')
                }
            }
        }

        stage('Push Docker Image (Optional)') {
           
            steps {
                script {
                    docker.withRegistry('https://registry.example.com', 'docker-hub-credentials') {
                        docker.image('lab-11-scd:latest').push('latest')
                    }
                }
            }
        }
    }
}

