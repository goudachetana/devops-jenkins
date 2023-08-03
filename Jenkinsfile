pipeline{
	//agent any
	agent {
	
	docker { image 'node:3.17-alpine' }
		}
	
	stages {
		stage('Build'){
		
		steps{
			echo "Build"
			sh 'node --version'
			}
			
		}
	
			
		
	stage('Test'){
		
		steps{
			
			echo "Test"
			
			}
			
		}
	
	
	stage('Integration Test'){
		
		steps{
			
			echo "Integration Test"
			}
			
		}
	}
	
	post{
		always{
			echo "Iam always run"
		}
		success{
			echo "Build and Testing is succesfull"
		}
		failure{
			echo "build and testing is failure"
		}
		
	}	
		
	
}
