pipeline {
	agent any
    /*agent { 
        docker { 
            image 'node:18.16.0-alpine'
            
        } 
    }*/
	
	stages {
		stage('Build'){
		
		steps{
			
			//sh 'node --version'
			echo "Build"
			echo "PATH - $PATH"
			echo "BUILD_NUMBER - $env.BUILD_NUMBER"
			echo "BUILD_ID - $env.BUILD_ID"
			echo "JOB_NAME - $env.JOB_NAME"
			echo "BUILD_TAG - $env.BUILD_TAG"
			echo "BUILD_URL - $env.BUILD_URL"
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
