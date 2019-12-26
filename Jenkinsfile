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
                      		 bat label: '', script: 'mvn clean deploy sonar:sonar'
               
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
