pipeline {
<<<<<<< HEAD
	agent any
	//agent {docker {image 'node:14.4.0'}}
=======
	//agent any
	agent { docker { image 'maven:3.6.3'} }
>>>>>>> abcdea5a2656941b6626cb01b6ad777f005daaf4
	stages{
		stage('Build'){
			steps{
				//sh 'node --version'
				echo'Build'	
				echo 'PATH - $PATH'
				echo 'BUILD_NUMBER - $env.BUILD_NUMBER'
				echo 'BUILD_ID - $env.BUILD_ID'
				echo 'JOB_NAME - $env.JOB_NAME'
				echo 'BUILD_TAG - $env.BUILD_TAG'
				echo 'BUILD_URL - $env.BUILD_URL'
			}
		}
		stage('test'){
			steps{
				echo 'Test'
			}
		}
		stage('Integration test'){
			steps{
				echo 'Integration Test'	
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

