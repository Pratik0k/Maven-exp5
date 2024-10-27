pipeline {
    agent any
    tools {
        maven 'Maven 3.9.9' // Use the name you gave in the Global Tool Configuration
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Pratik0k/Maven-exp5.git' // Replace with your repository
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
        }
    }
}
