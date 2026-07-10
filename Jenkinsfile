pipeline {
    agent any

    environment {
        JAVA_HOME = "C:\\Program Files\\Java\\jdk-25.0.3"
        PATH = "${JAVA_HOME}\\bin;${env.PATH}"
        IMAGE_NAME = "bharat20upadhayay/demo-app"
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Source code checked out successfully.'
            }
        }

        stage('Build') {
            steps {
                bat 'mvnw.cmd clean package'
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t %IMAGE_NAME%:%BUILD_NUMBER% .'
            }
        }

        stage('Docker Login') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    bat 'echo %DOCKER_PASS% | docker login -u %DOCKER_USER% --password-stdin'
                }
            }
        }

        stage('Docker Push') {
            steps {
                bat 'docker push %IMAGE_NAME%:%BUILD_NUMBER%'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl set image deployment/demo-app demo-app=%IMAGE_NAME%:%BUILD_NUMBER%'
            }
        }

        stage('Verify Rollout') {
            steps {
                bat 'kubectl rollout status deployment/demo-app'
            }
        }
    }

    post {
        success {
            echo 'Deployment completed successfully.'
        }

        failure {
            echo 'Deployment failed.'
        }
    }
}
  