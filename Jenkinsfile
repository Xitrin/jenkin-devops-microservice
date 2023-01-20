//SCRIPTED

//DECLARATIVE
pipeline {
	agent any
	// agent { docker { image 'node:19.4.0' } }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}

	stages {
		stage('Build') {
			steps {
				sh "mvn --version"
				sh "docker version"
				echo "Build"
				echo "$PATH"
				echo "Build Number - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
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

