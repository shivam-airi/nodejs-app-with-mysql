pipeline{
	agent any
	environment {
		DOCKERHUB_CREDENTIALS=credentials('dockerhub-node-app')
	}

	stages {
		stage('testing-101') {
			steps {
				sh 'pwd'
				sh 'ls -l'
			}
		}

	}
}
