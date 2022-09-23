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
				sh 'docker context create ecs myecs'				
			}
		}	
	}
	
		
}