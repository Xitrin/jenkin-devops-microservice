//SCRIPTED

//DECLARATIVE
pipeline {
	//agent any
	agent { docker { image 'maven:3.6.3' } }
	stages {
		stage('Build') {
			steps {
				sh "mvn --version"
				echo "Build"
			}
		}
		stage('Test') {
			steps {	
				echo "Test"
			}
		}
		stage('Integration Test') {
			steps {	
				echo "Integration Test"
			}
		}
	} 
	post {
		always {
			echo 'Im awesome. I run always ayaya'
		}
		success {
			echo 'only when successful'
		}
		failure {
			echo 'failure ayaya'
		}
		//changed
	}
}

