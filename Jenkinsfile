pipeline {
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
	}
}
