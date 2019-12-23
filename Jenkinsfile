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
	    		tool name: 'Maven', type: 'maven'
			clean install	
	    	}
	    }
	
	}
}
