node {
 	// Clean workspace before doing anything
    deleteDir()

    try {
        stage ('Clone') {
        	checkout scm
        }
        stage ('Build') {
        	sh "echo 'shell scripts to build project...'"
        }
        stage ('Tests') {
	        parallel 'static': {
	            sh "echo 'shell scripts to run static tests...'"
	        },
	        'unit': {
	            sh "echo 'shell scripts to run unit tests...'"
	        },
	        'integration': {
	            sh "echo 'shell scripts to run the integration tests...'"
	        }
        }
      	stage ('Deploy') {
            sh "echo 'shell scripts to deploying to the server...'"
      	}
    } catch (err) {
        currentBuild.result = 'FAILED'
        throw err
    }
}

