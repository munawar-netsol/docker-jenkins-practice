pipeline {
    agent any
	environment {
		dockerhub = credentials('dockerhub')
		AWS_CREDS = credentials('490814153332')
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
				sh 'docker context use default'
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
				sh 'echo $dockerhub_PSW | docker login -u $dockerhub_USR --password-stdin'
			}			
		}

		stage('Push') {

			steps {
				sh 'docker-compose push'
			}
		}
			
		stage('Deploy to ECS') {

			steps {				
				sh 'docker context create myecs --from-env'			
				sh 'docker context use myecs'
				sh 'docker compose --file docker-compose-ecs.yml up'
				sh 'docker compose ps --format json'
			}
		}	
	}
	post {
			always {
				sh 'docker logout'
			}
	}
		
}