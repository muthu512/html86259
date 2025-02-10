pipeline {
    agent { label 'ubuntuu' } // Runs on Ubuntu slave

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/muthu512/html86259.git'
            }
        }

        stage('Deploy to Nginx') {
            steps {
                sh '''
                sudo cp index.html /var/www/html/index.html
                sudo systemctl restart nginx
                '''
            }
        }
    }

    post {
        success {
            echo "Deployment successful!"
        }
        failure {
            echo "Deployment failed!"
        }
    }
}
