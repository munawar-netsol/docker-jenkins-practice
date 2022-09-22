pipeline {
    agent any
	stages
	{            
		stage('Four') {
			parallel {
				stage('Code Build') {
					steps {
						sh 'dotnet publish "JenkinsDockerPractice/ContractModificationService.csproj" -c Release -o JenkinsDockerPractice/app/publish'
						sh 'docker-compose down'
						sh 'docker-compose up --build -d'
					}
					
				}
			}
		}
	}
}