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
	    		bat label: '', script: 'mvn clean test'
			jacoco()
				
	    	}
	    }
		stage('Deploy') {
	    	steps {
	    		echo "Deploy"
	    	}
	    }	
	}
}
