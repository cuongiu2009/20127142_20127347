pipeline {
    agent any

    stages {
        stage('Build') {

			steps {
				sh 'docker build -t jenkins:latest .'
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
