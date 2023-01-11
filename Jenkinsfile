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
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
