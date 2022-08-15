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
		stage('Build'){
			steps{
				sh 'mvn --version'
				sh 'docker version'
				echo "Build"
				echo "path - $PATH"
				echo "buildnumber - $env.BUILD_NUMBER"				
				echo "build tag - $env.BUILD_TAG"
				echo "jenkinurl - $env.JENKINS_URL"
				echo "branch name -  $env.BRANCH_NAME"
			}
		}
		stage('Test'){
			steps{
				echo "Test"
				
			}
		}
		stage('Integration Test'){
			steps{
				echo "Interation Test"
			
			}
		}
	} 
	
	post {
		always{
			echo "I am awesome,. I always run"
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
