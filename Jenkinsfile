
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
                sh 'aws ecr get-login-password --region eu-north-1 | docker login --username AWS --password-stdin 798498373443.dkr.ecr.eu-north-1.amazonaws.com'
		sh 'docker build . -t amzn-linx-image'  
		sh 'docker tag amzn-linx-image:latest 798498373443.dkr.ecr.eu-north-1.amazonaws.com/docker-image-repo:latest'    
		sh 'docker push 798498373443.dkr.ecr.eu-north-1.amazonaws.com/docker-image-repo:latest'   
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
		
	}
	aborted {
		sh 'dockers ps'
	}
}	
}
