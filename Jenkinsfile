pipeline {
    agent any
	environment {
		dockerhub = credentials('dockerhub')
	}
	stages
	{     
		stage('Login') {

			steps {
				withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'pass', usernameVariable: 'user')]) {
					sh "echo $user"
					
				}
			}				
		}
				
	}
		
}