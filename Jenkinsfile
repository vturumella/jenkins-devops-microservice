pipeline {
	//agent any
	agent {docker {image 'node:14.4.0'}}
	stages{
		stage('Build'){
			steps{
				sh 'node --version'
				echo'Build'	
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

