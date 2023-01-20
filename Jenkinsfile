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
		stage('Checkout') {
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
		stage('Compile') {
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
			steps {	
				sh "mvn failsafe:integration-test failsafe:verify"
			}
		}
		stage('Package') {
			steps {	
				sh "mvn package -DskipTests"
			}
		}
		stage('Build Docker Image') {
			steps {
				//docker build -t xitrin/currency-exchange-devops:$env.BUILD_TAG
				script {
					dockerImage = docker.build("xitrin/currency-exchange-devops:${env.BUILD_TAG}")
				}
			}
		}
		stage('Push Docker Image') {
			steps {
				script {
					docker.withRegistry('', 'dockerhub') {
						dockerimage.push();
						dockerimage.push('latest');
					}
				}
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

