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
            input

{

message "Do you want to proceed for deployment ?"

}
            steps {
                echo 'Deploying...'
                // Add deployment steps here
            }
        }
    }
}
