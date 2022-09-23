pipeline {
    agent any
	stages
	{     
		stage('Deploy to ECS') {
			steps {				
				sh 'docker context use myecs'			
			}
		}	
	}
	post {
			always {
				sh 'docker logout'
			}
	}
		
}