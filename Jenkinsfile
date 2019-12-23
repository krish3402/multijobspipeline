pipeline {
	agent any
	tools { 
        maven 'Maven 3.3.9' 
        jdk 'jdk8' 
    }
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
