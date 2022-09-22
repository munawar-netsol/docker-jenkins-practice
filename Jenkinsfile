pipeline {
    agent any
	stages
	{            
		stage('Four') {
			parallel {
				stage('Code Build') {
					steps {
						sh 'dotnet build JenkinsDockerPractice/ContractModificationService.csproj'
					}
					
				}
			}
		}
	}
}