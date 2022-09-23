pipeline {
    agent any
	stages
	{     
		stage('Deploy to ECS') {
			steps {		
				sh 'pwd'
				sh 'docker context use myecscontext'			
			}
		}	
	}
		
}