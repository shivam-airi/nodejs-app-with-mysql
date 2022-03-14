pipeline{
	agent any
	environment {
		DOCKERHUB_CREDENTIALS=credentials("dockerhub-node-app")
	}

	stages {
		stage('Build image for frontend') {
			steps {
				sh "docker build -t frontend:v${env.BUILD_ID} frontend/."
			}
		}

		stage('Build image for backend') {
			steps {
				sh "docker build -t backend:v${env.BUILD_ID} backend/."
			}
		}
		
		stage('Login') {
			steps {
				sh "echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin"
			}
		}
	}
	
	post {
		always {
			sh "docker logout"
		}
	}
}
