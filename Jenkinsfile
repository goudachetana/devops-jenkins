pipeline {
	agent any
	
	environment{
    		dockerHome = tool 'docker_chetana'
    		maveenHome = tool 'maveen_chetana'
    		PATH="$dockerHome/bin:$maveenHome/bin:$PATH"
    		}
	
	
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
			//echo "compile"
			}
		}
	
			
		
	stage('Test'){
		
		steps{
			
			echo "Test"
			//sh "mvn test"
			
			}
		}
		
		stage('Integration Test'){
		
		steps{
			
			//echo "Integration Test"
			sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
	
		/*stage('Build Docker Image'){
		steps{
			//"docker build -t chetanagouda/microservices-jenkins:$env.BUILD_TAG"
			script{
			
				docker.build("chetanagouda/microservices-jenkins:${env.BUILD_TAG}")
			}
		}
	}*/
	
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
