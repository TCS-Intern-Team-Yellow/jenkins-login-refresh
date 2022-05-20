pipeline {
	agent any
	stages {
		stage('running image on docker') {
			steps {
				sshagent(['10.0.143.117']) {
				
				sh """ssh -o StrictHostKeyChecking=no ec2-user@10.0.143.117 << EOF   
				sudo docker stop loginservice
        sudo docker rm loginservice
        sudo docker pull js194/loginservice:latest
				sudo docker run -d --name loginservice js194/loginservice:latest
				exit
				EOF"""
				    
				}
			}
		}
	}
}
