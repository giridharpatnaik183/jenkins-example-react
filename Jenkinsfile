pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                echo "Switching to branch master"
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                echo "Building app..."
                sh 'npm install'
                sh 'npm run build'
            }
        }
        
        stage('Deploy') {
            steps {
                echo "Deploying files to Nginx directory..."
                sh 'scp -r build/* ubuntu@72.31.12.106:/var/www/72.31.12.106/'
            }
        }
    }
}
