pipeline {
    agent any

    environment {
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk-25.0.3'
        PATH = "${JAVA_HOME}\\bin;${env.PATH}"
    }

    stages {

        stage('Verify Java') {
            steps {
                bat 'echo JAVA_HOME=%JAVA_HOME%'
                bat 'java -version'
                bat 'javac -version'
            }
        }

        stage('Build') {
            steps {
                bat '.\\mvnw.cmd clean package'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }
}