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
	    		tool name: 'Maven', type: 'maven'
			clean install	
	    	}
	    }
	   	 stage('Deploy') {
	    		steps {
	    		echo "Deploy"	
	    	}
	    }
	}
}
