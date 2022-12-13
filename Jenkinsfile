pipeline {
	agent { docker { image 'maven:3.3.3'} 	}
	stages {
		stage('log version info') {
			environment {
                  HOME="C:/ProgramData/Jenkins/.jenkins"
                }
			steps {
				sh 'mvn --version'
				sh 'mvn clean install'
			}
		}
	} 
}
