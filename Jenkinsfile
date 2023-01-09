pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                git branch: 'main', url: 'https://github.com/cuongiu2009/20127142_20127347.git'
            }
        }
        stages('Docker'){
            withDockerRegistry(credentialsId: 'dockerhub', url: 'https://index.docker.io/v1/') {
                sh 'docker build -t 20127142/20127142_20127347:v10 .'
                sh 'docker push 20127142/20127142_20127347:v10 .'
            }
        }
    }
}
