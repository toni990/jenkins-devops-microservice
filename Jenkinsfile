//DECLARATIVE
pipeline {
	 agent { docker { image 'maven:3.8.1' } }
	 stages{
		stage('Build') {
		  steps{
			  sh "mvn --version"
		  }
		}
		stage('Test') {
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
}