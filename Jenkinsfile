
pipeline {
    agent any
    

    stages {
       
        stage('copying') {
            steps {
                echo 'copying...'
                //git url: 'https://github.com/Naresh100893/amazon-image.git', branch: 'main'
            }
        }


    
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'docker build -t amazonImageNew .'
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
                    return env.BRANCH_NAME == 'master'
                }
            }
            steps {
                echo 'Deploying...'
                // Add deployment steps here
            }
        }
    }
}
