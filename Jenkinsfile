pipeline {
	agent any
	environment {
			GIT_REPOSITORY_URL='https://github.com/artisadbhaye/jenkins-py.git'
	}
	stages {
		stage('clone repo') {
			steps {
				try{
					git branch: 'master', url: GIT_REPOSITORY_URL	
				}catch(Exception e){
					echo "Failed to clone repo ${e.message}"
					echo "Failed to clone repo"
				}
			}
		}
		stage('execute file') {
			steps {
				try{
					sh """
					python3 hello.py
					"""
				}catch(Exception e){
					echo "Could not run sorry: ${e.message}"
					echo "Could not run"
				}
			}
		}
	}
}
