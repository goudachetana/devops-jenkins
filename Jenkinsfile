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
			
			
			echo "Build"
			echo "PATH - $PATH"
			echo "BUILD_NUMBER - $env.BUILD_NUMBER"
			echo "BUILD_ID - $env.BUILD_ID"
			echo "JOB_NAME - $env.JOB_NAME"
			echo "BUILD_TAG - $env.BUILD_TAG"
			echo "BUILD_URL - $env.BUILD_URL"
			} 
			
		}
	stage('Compile'){
		steps{
			sh "mvn clean compile"
			}
		}
	
			
		
	stage('Test'){
		
		steps{
			
			echo "Test"
			//sh "mvn test"
			
			}
			
		}
	
	
	
		
	/
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
