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
                bat 'mvn sonar:sonar -Dsonar.projectKey=sast-demo -Dsonar.host.url=http://localhost:9000 -Dsonar.login=%SONAR_TOKEN%'
            }
        }
    }
}
