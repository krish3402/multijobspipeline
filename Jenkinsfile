pipeline {
	agent any
	stages {
		stage('Jacoco Coverage Report') {
			steps {
				jacoco()
			}
		}
    stage('Jacoco XML Report') {
      steps {
       publishCoverage adapters: [jacocoAdapter(mergeToOneReport: true, path: 'maven-simple/target/site/jacoco-aggregate/jacoco.xml', thresholds: [[thresholdTarget: 'Aggregated Report']]), jacocoAdapter(mergeToOneReport: true, path: 'module-1/target/site/jacoco-aggregate/jacoco.xml'), jacocoAdapter(mergeToOneReport: true, path: 'module-2/target/site/jacoco-aggregate/jacoco.xml')], sourceFileResolver: sourceFiles('NEVER_STORE')
      }
    }
	}
}
