pipeline {
	agent any	
	stages {
		stage('Build') {
			steps {
				bat label: '', script: 'mvn clean install'
			}
		}
	   	 stage('Test') {
	    		steps {
	    		bat label: '', script: 'mvn clean test'
	    	}
	    }
		stage('Deploy') {
	    	steps {
	    		echo "Deploy"
	    	}
	    }	
	}
}
