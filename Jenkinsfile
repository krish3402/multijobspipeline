pipeline {
	agent any	
	stages {
		stage('Build') {
			steps {
				git 'https://github.com/krish3402/multijobspipeline.git'
			}
		}
	   	 stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('My SonarQube Server') {
                sh 'mvn clean deploy sonar:sonar'
              }
            }
          }         
		
		stage('Deploy') {
	    	steps {
	    		bat label: '', script: 'deploy.bat'
	    	}
	    }	
	
	}
}
