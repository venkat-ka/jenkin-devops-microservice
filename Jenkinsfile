pipeline {
	agent any
	//agent{
//		docker {
//			image 'node:18.7'
//		}
//	}
	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Checkout'){
			steps{
				sh 'mvn --version'
				
				echo "Build"
				echo "path - $PATH"
				echo "buildnumber - $env.BUILD_NUMBER"				
				echo "build tag - $env.BUILD_TAG"
				echo "jenkinurl - $env.JENKINS_URL"
				echo "branch name -  $env.BRANCH_NAME"
			}
		}
		stage('Compile'){
			steps{
				sh "mvn clean compile"
			}
		}
		stage('Test'){
			steps{
				sh "mvn test"
				
			}
		}
		stage('Integration Test'){
			steps{
				sh "mvn failsafe:integration-test failsafe:verify"
			
			}
		}

		stage('Package'){
			steps{
				sh "mvn package -DskipTests"
			
			}
		}
		stage('Checking Custom Ven'){
		steps{
			sh "java --version"
			sh  "echo 'Venkat Checking'"
		
		}
	}


		stage('Build Docker Image'){
			steps{
				//"docker build -t venkatkrish/jenkcurrency-exchange:$env.BUILD_TAG"
				script{
					dockerImag = docker.build("venkatkrish/jenkcurrency-exchange:${env.BUILD_TAG}")
				}
			}
		}
		stage('Build Docker push'){
			steps{
				//"docker build -t venkatkrish/jenkcurrency-exchange:$env.BUILD_TAG"
				script{
						docker.withRegistry('','dockerhub'){
							dockerImag.push()
							dockerImag.push('latest') 
					}
				}
			}
		}
		
	} 
	
	post {
		always{
			echo "I am awesome,. I always run updartes"
		}
		success{
			echo "I run when successfull"
		}
		failure{
			echo "I run when fiailure"
		}
		// other state is changed
	}
}
