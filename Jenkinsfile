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
                     sh 'rsync -avh -e "ssh -i /var/lib/jenkins/OregonKey.pem" /var/lib/jenkins/workspace/Pipeline/ ubuntu@10.0.2.248:/home/ubuntu/app/'
         }
       }
    }
}
