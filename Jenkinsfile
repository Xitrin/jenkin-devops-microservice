//SCRIPTED

//DECLARATIVE
pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
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
	}
}

