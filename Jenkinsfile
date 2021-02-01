pipeline {
    agent any
    stages {
	    stage('SCM Checkout'){
		    steps{
		    git 'https://github.com/DanishShaikh-787/new_chatapp'
		 }
	    }
	    
            stage('build') {
               steps {
                     bash 'rsync -avh -e "ssh -i /var/lib/jenkins/OregonKey.pem" /var/lib/jenkins/workspace/Pipline1 ubuntu@10.0.2.248:/home/ubuntu/app/'
         }
       }
    }
}
