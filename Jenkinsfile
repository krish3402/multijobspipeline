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
	    		bat label: '', script: 'mvn clean install'
			jacoco()
			publishCoverage adapters: [jacocoAdapter(mergeToOneReport: true, path: 'maven-simple/target/site/jacoco-aggregate/jacoco.xml', thresholds: [[thresholdTarget: 'Aggregated Report']]), jacocoAdapter(mergeToOneReport: true, path: 'module-1/target/site/jacoco-aggregate/jacoco.xml'), jacocoAdapter(mergeToOneReport: true, path: 'module-2/target/site/jacoco-aggregate/jacoco.xml')], sourceFileResolver: sourceFiles('NEVER_STORE')
				
	    	}
	    }
		stage('Deploy') {
	    	steps {
	    		echo "Deploy"
	    	}
	    }	
	}
}
