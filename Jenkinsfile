pipeline {
	agent { docker { image 'maven:3.3.3'} 	}
	stages {
		stage('log version info') {
			steps {
				sh 'mvn --version'
				sh 'mvn clean install'
			}
		}
	}
	post {
        // Clean after build
        always {
            cleanWs(cleanWhenNotBuilt: false,
                    deleteDirs: true,
                    disableDeferredWipeout: true,
                    notFailBuild: true,
                    patterns: [[pattern: '.gitignore', type: 'INCLUDE'],
                               [pattern: '.propsfile', type: 'EXCLUDE']])
        }
    }

}
