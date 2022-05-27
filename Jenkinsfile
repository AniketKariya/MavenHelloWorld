pipeline {
	// testing webhook
	agent any
	
	environment {
        	EMAIL_TO = 'aniket.kariya@gmail.com'
    	}
	
	stages {
		stage('-- CLEAN --') {
			steps {
				echo "Cleaning..."
				bat "mvn clean"
			}
		}
		
		stage('-- TEST --') {
			steps {
				echo "Testing..."
				bat "mvn test"
			}
		}
		
		stage('-- BUILD --') {
			steps {
				echo "Building..."
				bat "mvn package"
			}
		}
	}
	
	post {
		failure {
            		emailext body: 'Check console output at $BUILD_URL to view the results. \n\n ${CHANGES} \n\n -------------------------------------------------- \n${BUILD_LOG, maxLines=100, escapeHtml=false}', 
				to: "${EMAIL_TO}", 
				subject: 'Build failed in Jenkins: $PROJECT_NAME - #$BUILD_NUMBER'
        	}
		unstable {
            		emailext body: 'Check console output at $BUILD_URL to view the results. \n\n ${CHANGES} \n\n -------------------------------------------------- \n${BUILD_LOG, maxLines=100, escapeHtml=false}', 
                    		to: "${EMAIL_TO}", 
               			subject: 'Unstable build in Jenkins: $PROJECT_NAME - #$BUILD_NUMBER'
        	}
       		changed {
			emailext body: 'Check console output at $BUILD_URL to view the results. \n\n ${CHANGES} \n\n -------------------------------------------------- \n${BUILD_LOG, maxLines=100, escapeHtml=false}', 
				to: "${EMAIL_TO}", 
				subject: 'Jenkins build is back to normal: $PROJECT_NAME - #$BUILD_NUMBER'
		}
		success {
			emailext body: 'Check console output at $BUILD_URL to view the results. \n\n ${CHANGES} \n\n -------------------------------------------------- \n${BUILD_LOG, maxLines=100, escapeHtml=false}', 
				to: "${EMAIL_TO}", 
				subject: 'Jenkins build is successful: $PROJECT_NAME - #$BUILD_NUMBER'
		}
	}
}
