pipeline {
	//agent any
	agent{
		docker {
			image: 'maven:3.6.3'
		}
	}
	stages{
		stage('Build'){
			steps{
				sh 'mvn --version' 
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
		// other state is changed
	}
}
