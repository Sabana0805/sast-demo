pipeline {
    agent any
    tools {
        jdk 'jdk'
        maven 'mvn'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    bat 'mvn sonar:sonar -Dsonar.projectKey=sast-demo -Dsonar.projectName=SAST-Demo'
                }
            }
        }
    }
}
