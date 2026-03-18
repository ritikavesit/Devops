pipeline {
    agent { label 'maven-node' }

    tools {
        maven 'Maven3'
        jdk 'JDK21'
    }

    stages {

        stage('Clone') {
            steps {
                git url:'https://github.com/ritikavesit/Devops',
                     branch: 'main'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
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
