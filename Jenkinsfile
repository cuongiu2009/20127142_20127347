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
                sh 'docker build -t advanced-network-jenkins:latest .'
            }
        }
    }
}
