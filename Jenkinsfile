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
	stage('Test') {
	    steps {
		sh 'grep "Olha Malynovska" index.html'
	    }
        }
	stage('Deploy') {
	    steps {
		sh '''
		scp -o StrictHostKeyChecking=no index.html ubuntu@3.108.219.146:/home/ubuntu
		'''
	    }
	}
    }
}
