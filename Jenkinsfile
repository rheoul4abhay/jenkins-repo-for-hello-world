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
			sh 'grep "Abhay Shrivastava" index.html'
			}
        }
		stage('Deploy') {
	    	steps {
			sshagent(['ec2-ssh-key']) {
                    sh '''
		    		scp -o StrictHostKeyChecking=no index.html ubuntu@3.108.219.146:/home/ubuntu
		    		ssh -o StrictHostKeyChecking=no ubuntu@3.108.219.146 'sudo mv /home/ubuntu/index.html /var/www/html/index.html'
             	    '''
	   			}
	    	}
		}
    }
}
