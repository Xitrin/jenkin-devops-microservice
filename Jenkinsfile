//SCRIPTED

//DECLARATIVE
pipeline {
	//agent any
	agent { docker { image 'node:19.4.0' } }
	stages {
		stage('Build') {
			steps {
				//sh "mvn --version"
				sh "node --version"
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

