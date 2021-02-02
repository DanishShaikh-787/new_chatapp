pipeline {
    agent any
    stages {
	    stage('SCM Checkout'){
		    steps{
		    git 'https://github.com/DanishShaikh-787/new_chatapp'
		 }
	    }
	    
	    stage('Sonarqube') {
    environment {
        scannerHome = tool 'sonar_scanner'
    }
    steps {
        withSonarQubeEnv('sonar_scanner') {
            sh "${scannerHome}/bin/sonar-scanner"
        }
	    timeout(time: 5, unit: 'MINUTES') {
            waitForQualityGate abortPipeline: true
	    
        }
    }
}
            stage('build') {
               steps {
                     sh 'rsync -avh -e "ssh -i /var/lib/jenkins/OregonKey.pem" /var/lib/jenkins/workspace/Pipline1 ubuntu@10.0.2.248:/home/ubuntu/app/'
         }
       }
    }
}
