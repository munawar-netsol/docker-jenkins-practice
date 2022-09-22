pipeline {
    agent any
	stages
	{            
		stage('Four') {
			parallel {
				stage('Code Build') {
					steps {
						sh 'docker compose down'
						sh 'docker container prune'
						
						sh 'dotnet publish "JenkinsDockerPractice/ContractModificationService.csproj" -c Release -o JenkinsDockerPractice/app/publish'
						
						sh 'docker-compose up --build -d'
					}
					
				}
			}
		}
	}
}