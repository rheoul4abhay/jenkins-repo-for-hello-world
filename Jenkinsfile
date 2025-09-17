pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/rheoul4abhay/jenkins-repo-for-hello-world.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the application'
                sh 'cat index.html'
            }
        }
    }
}
