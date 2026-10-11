pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('Docker_access')
        IMAGE_NAME = 'majortife/flask-portfolio-app'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/majortife/Jenkins-Flask-app.git'
                 }
        }
        stage('Run Lint Test') {
            steps {
                sh 'pip3 install --break-system-packages flake8'
                sh 'flake8 . || true'
                  }
            }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME:$BUILD_NUMBER .'
            }
        }

        stage('Push to DockerHub') {
            steps {
                script {
                    sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
                    sh 'docker push $IMAGE_NAME:$BUILD_NUMBER'
                }
            }
        }

        stage('Deploy to Stage') {
            steps {
                sh 'docker run -d -p 5002:5000 $IMAGE_NAME:$BUILD_NUMBER'
            }
        }
    }

    post {
        success { echo '✅ Build, Test, and Deploy completed successfully!' }
        failure { echo '❌ Pipeline failed. Check logs.' }
    }
}
