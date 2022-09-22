pipeline {
    agent any
	environment {
		dockerhub = credentials('dockerhub')
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
		stage('Login') {

			steps {
				withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'pass', usernameVariable: 'user')]) {
					sh "echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin"					
				}
			}				
		}

		stage('Push') {

			steps {
				sh 'docker-compose push'
			}
		}
				
	}
	post {
			always {
				sh 'docker logout'
			}
	}
		
}