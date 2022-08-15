pipeline {
	agent any
	//agent{
//		docker {
//			image 'node:18.7'
//		}
//	}
	stages{
		stage('Build'){
			steps{
				
				echo "Build"
				echo "path - $env.PATH"
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
