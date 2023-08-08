pipeline {
	agent any
    /*agent { 
        docker { 
            image 'node:18.16.0-alpine'
            
        } 
    }*/
    	environment{
    		dockerHome = tool 'docker_chetana'
    		maveenHome = tool 'maveen_chetana'
    		PATH="$dockerHome/bin:$maveenHome/bin:$PATH"
    		}
	
	stages {
		stage('Build'){
		
		steps{
			
			//sh 'node --version'
			sh 'mvn --version'
			sh 'docker version'
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
	
	
	stage('Integration Test'){
		
		steps{
			
			//echo "Integration Test"
			sh "mvn failsafe:integration-test failsafe:verify"
			}
			
		}
		
	stage('package'){
		
		steps{
			
			
			sh "mvn package DskipTests"
			}
			
		}	
		
		
		
		
	stage('Build Docker Image'){
		steps{
			//"docker build -t chetanagouda/microservices-jenkins:$env.BUILD_TAG"
			script{
			
				dockerImage=docker.build("chetanagouda/microservices-jenkins:${env.BUILD_TAG}")
			}
		}
	}
	
	stage('Push Docker Image'){
		steps{
			scripts{
				docker.withRegistry('', dockerhub){
					dockerImage.push();
					dockerImage.push('latest');
				}
			}
		
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
