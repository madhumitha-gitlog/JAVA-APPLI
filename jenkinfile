pipeline {
    agent any

    tools {
        jdk 'JDK 21'
        maven 'Maven3'
    }

    stages {
        stage('Clone') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/jegalinjasmi-jega/java-cicd-project.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar'
            }
        }
    }

    post {
        success {
            echo 'Java CI/CD Successful'
        }

        failure {
            echo 'Java CI/CD Failed'
        }
    }
}
