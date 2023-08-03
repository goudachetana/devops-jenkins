pipeline{
	agent any
	stages{
		stage('Build'){
		
		steps{
			echo "Build"
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
