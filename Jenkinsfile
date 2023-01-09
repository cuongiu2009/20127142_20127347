pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                git branch: 'main', url: 'https://github.com/cuongiu2009/20127142_20127347.git'
            }
        }
        stages('Docker'){
            steps{
                withDockerRegistry(credentialsId: 'dockerhub', url: 'https://index.docker.io/v1/') {
                    sh label:",script: 'docker build -t 20127142/20127142_20127347:v10 .'
                    sh label:",script: 'docker push 20127142/20127142_20127347:v10 .'
                }
            }
        }
    }
}
