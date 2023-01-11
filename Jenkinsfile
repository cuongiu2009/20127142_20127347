pipeline {
    agent any

    stages {
        stage('Docker build') {
	        steps {
		        sh 'docker build -t jenkins:latest .'
	        }
	    }
        stage('View Images') {
			steps {
				sh 'docker images'
			}
		}
	
        stage('Build') {
            steps {
                echo 'Building..'
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
}
