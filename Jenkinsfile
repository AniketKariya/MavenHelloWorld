pipeline {
	agent any
	
	stages {
		stage('-- CLEAN --') {
			steps {
				echo "Cleaning..."
				bat mvn clean
			}
		}
		
		stage('-- TEST --') {
			steps {
				echo "Testing..."
				bat mvn test
			}
		}
		
		stage('-- BUILD --') {
			steps {
				echo "Building..."
				bat mvn build
			}
		}
	}
}
