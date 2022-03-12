pipeline{
	agent any

	stages {
		stage('Testing-101'){
			steps {
				sh "pwd"
				sh "ls -l"
			}
		}

		stage('Build image for frontend') {
			steps {
				sh "cd frontend/"
				sh "pwd"
				sh "docker build -t frontend:${env.BUILD_ID} ."
			}
		}
	}
}
