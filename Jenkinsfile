pipeline {
    agent any
    stages {
        stage('Download-Code-GIT') {
            steps {
                echo "Download code from git"
                git branch: 'main', url: 'https://github.com/technomineitdevelopment/maven-jenkins10.git'
            }
        }
        stage('Build Docker Image') {
            steps {
            echo "Build the application docker image and push to Docker Hub"    
            sh '''docker build -t dockerusn/java-application:v${BUILD_NUMBER} .
            docker tag dockerusn/java-application:v${BUILD_NUMBER} dockerusn/java-application:latest
            docker push dockerusn/java-application:v${BUILD_NUMBER}
            docker push dockerusn/java-application:latest'''
            }
        }
    }
}
