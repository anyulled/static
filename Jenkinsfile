pipeline {
	agent any
	stages {
	    stage('Lint HTML'){
	        steps{
	            sh 'tidy -q -e *.html'
	        }
	    }
		stage('Upload to AWS'){
            withAWS(region:'eu-west-3') {
                s3Upload(file:'index.html', bucket:'udacity-jenkins-bucket', path:'index.html')
        }
		}
	}
}