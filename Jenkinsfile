pipeline {
    agent any
	stages
	{            
		stage('Code Build') {
			steps {
				sh 'dotnet publish "JenkinsDockerPractice/ContractModificationService.csproj" -c Release -o JenkinsDockerPractice/app/publish'
			}
			
		}
		stage('Code Compose') {
			steps {
				sh 'docker-compose up --build -d'
			}
			
		}
	}
}