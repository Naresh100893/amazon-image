
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
                //sh 'docker rm -f $(docker ps -aq)'
                sh "docker build . -t naresh7724/amazon-image-new:latest"
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
           
            steps {
                echo 'Deploying...'
                // Add deployment steps here
		    sh 'docker run -itd naresh7724/amazon-image-new:latest'
		    
            }
        }

        stage("docker-images-cleanup") {
	steps {
		sh "docker image prune -af"
	}
}

    }
post {
	always {
		sh "docker images"
		sh "docker container ls"
	}
}	
}
