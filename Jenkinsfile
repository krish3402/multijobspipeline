pipeline {
	agent any	
	stages {
		stage('Build') {
			steps {
				git 'https://github.com/krish3402/multijobspipeline.git'
			}
		}
	   	 stage('Test') {
	    		steps {
	    		bat label: '', script: 'mvn clean install'
				
	    	}
	    }
		stage('Deploy') {
	    	steps {
	    		echo "Deploy"
	    	}
	    }	
	}
}
