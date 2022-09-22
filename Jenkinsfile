pipeline {
    agent any
	stages
	{     

		stage('Code Build') {
			steps {
				sh 'dotnet publish "JenkinsDockerPractice/ContractModificationService.csproj" -c Release -o JenkinsDockerPractice/app/publish'
			}
			
		}
		stage('Cleanup') {
			steps {
				sh 'docker-compose down'
			}
			
		}	
		stage('Code Compose') {
			steps {
				sh 'docker-compose up --build -d'
			}
			
		}
	}
}