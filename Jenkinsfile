pipeline {
	agent any	
	stages {
		stage('Build') {
			steps {
				git 'https://github.com/krish3402/multijobspipeline.git'
			}
		}
	   	 stage('build && SonarQube analysis') {
            steps {
                withSonarQubeEnv('My SonarQube Server') {
                    // Optionally use a Maven environment you've configured already
                    withMaven(maven:'Maven 3.5') {
                        sh 'mvn clean deploy sonar:sonar'
                    }
                }
            }
        }
		stage('Deploy') {
	    	steps {
	    		echo "Deploy"
	    	}
	    }	
	}
}
