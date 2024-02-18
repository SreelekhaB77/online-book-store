pipeline {
    agent any
    
    environment {
        // Define Docker image name and tag
        DOCKER_IMAGE_NAME = 'mybookstore'
        DOCKER_IMAGE_TAG = 'latest'
    }
    
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SreelekhaB77/online-book-store.git'
            }
        }
        stage('build') {
            steps {
                sh 'mvn clean install'
            }
        }
        
        stage('Build Docker Image') {
            steps {
                // Build Docker image
                
            sh 'docker build -t mybookstore .'
                
            }
        }
        
        stage('Run Docker Container') {
            steps {
                // Run Docker container
                
                    sh'docker run -d -p 8000:8000 mybookstore'
              
            }
        }
    }
}
