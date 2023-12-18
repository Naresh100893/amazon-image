pipeline {
    agent any
	

    stages {
		
		stage('copy') {
            steps {
                echo 'copying...'
            }
        }
		
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
            when {
                expression {
                    // Define your condition here
                    return env.BRANCH_NAME == "origin/main"
                }
            }
            steps {
                echo 'Deploying...'
                // Add deployment steps here
            }
        }
    }
}
