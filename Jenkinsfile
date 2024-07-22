pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git branch: 'main', url:'https://github.com/Darius-Lim-zh/JenkinsDependencyCheckTest.git'
			}
		}

		stage('OWASP Dependency-Check Vulnerabilities') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default '
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}
