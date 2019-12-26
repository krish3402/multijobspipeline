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
								
	    		bat label: '', script: 'mvn clean deploy sonar:sonar  -Dsonar.projectName=multimodule'
			
			jacoco()
			publishCoverage adapters: [jacocoAdapter(mergeToOneReport: true, path: 'maven-simple/target/site/jacoco-aggregate/jacoco.xml', thresholds: [[thresholdTarget: 'Aggregated Report']]), jacocoAdapter(mergeToOneReport: true, path: 'module-1/target/site/jacoco-aggregate/jacoco.xml'), jacocoAdapter(mergeToOneReport: true, path: 'module-2/target/site/jacoco-aggregate/jacoco.xml')], sourceFileResolver: sourceFiles('NEVER_STORE')
			publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'maven-simple/target/site/jacoco-aggregate/', reportFiles: 'index.html', reportName: 'maven-simple Report', reportTitles: ''])
			publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'module-1/target/site/jacoco-aggregate/', reportFiles: 'index.html', reportName: 'module-1 Report', reportTitles: ''])
			publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'module-2/target/site/jacoco-aggregate/', reportFiles: 'index.html', reportName: 'module-2 Report', reportTitles: ''])
				
	    	}
	    }
		stage('Deploy') {
	    	steps {
	    		echo "Deploy"
	    	}
	    }	
	}
}
