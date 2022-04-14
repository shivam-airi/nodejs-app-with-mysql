
pipeline {
    agent any
    environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub')
	}
    
    stages {
//         stage('gitclone') {
//             steps {
//                 git "https://github.com/Naveenmishra1197/nodejs-app-with-mysql.git"
//             }
//         }
        stage('build frontend image') {
            steps {
               sh "docker build -t naveenmishra1197/frontend:v1 frontend/."

            }
        }
        stage('build backend image') {
            steps {
                sh "docker build -t naveenmishra1197/backend:v1 backend/."
            }
        }
         
        stage('build database image') {
            steps {
                sh "docker build -t naveenmishra1197/mysqldb:v1 mysqldb/."
            }
        }
      
        stage('login dockerhub') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
         stage('push images') {
            steps {
                sh 'docker push naveenmishra1197/frontend:v1'
                sh 'docker push naveenmishra1197/backend:v1'
                sh 'docker push naveenmishra1197/mysql:v1'
            }
        }
    }
}


