pipeline {
    agent any

    stages {

		stage('Build') {

			steps {
				sh 'docker build -t jenkins:latest .'
			}
		}

		stage('Login') {

			steps {
				sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
			}
		}
		
		
		stage('View Images') {

			steps {
				sh 'docker images'
			}
		}
		
		stage('Docker Tag') {

			steps {
				sh 'docker tag jenkins 20127142/jenkins'
			}
		}

		stage('Push') {

			steps {
				sh 'docker push 20127142/jenkins'
			}
		}
		
		stage('Remove current container if it exists') {

			steps {
				sh 'docker rm -f jenkins-mmt || true'
			}
		}
		
		stage('Run in Container') {

			steps {
				sh 'docker run --publish 3000:3000 --name jenkins-mmt -d --rm 20127142/jenkins:latest'
			}
		}
	}

	post {
		always {
			sh 'docker logout'
		}
	}
}
