pipeline{
	agent any

	stages {
		stage('Build image for frontend') {
			steps {
				sh "docker build -t frontend:v${env.BUILD_ID} frontend/."
			}
		}

		stage('Build image for backend') {
			steps {
				sh "docker build -t backend:v${env.BUID_ID} backend/."
			}
		}

	}
}
