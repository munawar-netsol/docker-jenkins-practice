pipeline {
    agent any
	environment {
		dockerhub = credentials('dockerhub')
		AWS_CREDS = credentials('490814153332')
	}
	stages
	{     
		stage('Deploy to ECS') {

			steps {	
			    sh 'sudo -su ec2-user'				
				sh 'docker context use myecs'
				sh 'sudo -su jenkins'				
			}
		}	
	}
	
		
}