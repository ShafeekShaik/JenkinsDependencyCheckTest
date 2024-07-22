pipeline {
	agent any
	stages {
    	stage('Checkout SCM') {
        	steps {
            	git 'https://github.com/ShafeekShaik/JenkinsDependencyCheckTest.git' 
        	}
    	}

    	stage('OWASP Dependency-Check Vulnerabilities') {
  	steps {
    	dependencyCheck additionalArguments: '''
                	-o './'
                	-s './'
		 	-n './'
                	-f 'ALL'
                	--prettyPrint''', odcInstallation: 'OWASP Dependency-Check Vulnerabilities'
   	 
    	dependencyCheckPublisher pattern: 'dependency-check-report.xml'
  	}
	}
  }
}
