pipeline {
    agent any
    tools {
        maven 'Maven3' // Use the name you gave in the Global Tool Configuration
    }
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/your-repo/maven-project.git' // Replace with your repository
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
