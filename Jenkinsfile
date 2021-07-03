//DECLARATIVE
pipeline {
	agent any
	//agent { any {image 'maven:3.8.1'} }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Checkout') {
		steps{
			sh 'mvn --version'
			sh 'docker version'
			echo "Build"
			echo "PATH - $PATH"
			echo "BUILD-NUMBER - $env.BUILD_NUMBERS"
			echo "BUILD_ID - $env.BUILD_ID"
			echo "BUILD_TAG - $env.BUILD_TAG"
			echo "BUILD-URL - $env.BUILD_URL"
     	}
	  }

	  stage('Compile'){
		  steps {
			  sh "mvn clean compile"

		  }
	  }
	
	   stage('Test') {
		  steps {
		      sh "mvn test"
		
     	}
	  }
	   stage('Integration Test') {
		   steps{
		      sh "mvn failsafe:integration-test failsafe:verify"
     	}
	  }
   }
   
   post {
	   always {
		   echo 'Im awesome. I run always'
	   }
	   success{
		   echo 'I run when you are successful'
	   }
	   failure {
		   echo 'I run when you fail'
	   }
   }
}