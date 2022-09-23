pipeline {
    agent any
	stages
	{     
		stage('Deploy to ECS') {
			steps {		
				sh 'echo $USER'
				sh 'docker context use ecs2'			
			}
		}	
	}
		
}