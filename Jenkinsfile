ipeline {

    agent any

   
    stages {
         stage('dependencies') {
          steps {
              sh 'npm install'
            }
          }

        stage('build') {
            steps {
                sh 'npm run build'
            }
        }
       
        stage('Docker Image') {
            steps {
               
                    sh "echo docker_build_-t_SCD-Lab11"
               
            }
        }
       
        stage('Docker Comopse Up') {
            steps {
               
                    sh "echo sudo-docker-compose-up"
               
            }
        }
    }
}
