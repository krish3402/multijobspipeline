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
	    		echo "Test"
	    	}
	    }
	    stage('Deploy') {
	    	steps {
	    		echo "Deploy"
	    	}
	    }
	}
}
