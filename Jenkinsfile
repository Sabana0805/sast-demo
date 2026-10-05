pipeline {
    agent any
    tools {
        jdk 'jdk'
        maven 'mvn'
    }
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('SonarQube') {
                    bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.11.0.3922:sonar -Dsonar.projectKey=sast-demo -Dsonar.projectName=sast-demo'
                }
            }
        }
    }
}
