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
			jacoco()
			publishCoverage adapters: [jacocoAdapter(mergeToOneReport: true, path: 'maven-simple/target/coverage-reports/jacoco-ut.exec	', thresholds: [[thresholdTarget: 'Aggregated Report']]), jacocoAdapter(mergeToOneReport: true, path: 'module-1/target/coverage-reports/jacoco-ut.exec	'), jacocoAdapter(mergeToOneReport: true, path: 'module-2/target/coverage-reports/jacoco-ut.exec	')], sourceFileResolver: sourceFiles('NEVER_STORE')
	    	}
	    }
	    stage('Deploy') {
	    	steps {
	    		echo "Deploy"
	    	}
	    }
	}
}
