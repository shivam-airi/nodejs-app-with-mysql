pipeline{
	agent any
	environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub-node-app')
	}

	stages {
		stage('Build image for frontend') {
			steps {
				sh 'cd frontend/'
				sh 'docker build -t frontend:${env.BUILD_ID} .'
			}
		}

	}
}
