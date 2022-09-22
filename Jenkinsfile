pipeline {
    agent any
	environment {
		DOCKER_HUB_CREDS = credentials('munawersheikh')
	}
	stages
	{     

		stage('Code Build') {
			steps {
				sh 'dotnet publish "JenkinsDockerPractice/ContractModificationService.csproj" -c Release -o JenkinsDockerPractice/app/publish'
			}
			
		}
		stage('Cleanup') {
			steps {
				sh 'docker system prune --force'
			}
			
		}	
		stage('Docker Compose') {
			steps {
				sh 'docker-compose up --build -d'
			}			
		}
		
		
		stage('Docker Push') {
			steps {
				sh 'docker-compose push'
			}			
		}
		
		
	}
}