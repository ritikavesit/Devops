pipeline {
    agent { label 'maven-node' }

    tools {
        maven 'Maven3'
        jdk 'JDK21'
    }

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/yourusername/yourrepo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn clean package'
            }
        }
    }

    post {
        success {
            echo 'Build Successful!'
        }
        failure {
            echo 'Build Failed!'
        }
    }
} 
