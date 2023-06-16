pipeline {
	agent any
	//agent {docker {image 'node:14.4.0'}}
	environment {
  		dockerHome = tool "myDocker"
		mavenHome = tool "myMaven"
  		PATH =  "$dockerHome/bin:$mavenHome/bin:$PATH"

	}

	stages{
		stage('checkout'){
			steps{
				sh 'mvn --version'
				sh 'docker --version'
				echo 'Build'	
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
			}
		}
		stage('build') {
  			steps {
    			sh "mvn clean install"
 			}
		}
		stage('test'){
			steps{
				sh "mvn test"
			}
		}
		stage('Integration test'){
			steps{
				sh "mvn failsafe:integration-test failsafe:verify"	
			}
		}
		stage('Build a Package') {
  			steps {
    			sh "mvn package -DskipTest "
 			}
		}
		stage('Build Docker Image') {
  			steps {
    			//docker build -t vthurimella/currency-exchange-devops:$env.BUILD_TAG
				script {
					dockerImage=docker.build("vthurimella/currency-exchange-devops:${env.BUILD_TAG}")
				}
  			}
		}
		stage('Push Docker Image') {
  			steps {
    			script {
					docker.withRegistry('','Dockerhub'){
					buildImage,push{};
					buildImage.push('latest');
					}
				}
  			}
		}
	}
	post{
		always{
			echo 'I always rub'
		}
		success{
			echo " i run whem am successful"

		}
		failure{
			echo ' I run when i fail'
		}
	}
}

