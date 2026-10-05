pipeline {
    agent any
    tools {
        jdk 'jdk17'
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
                bat 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.11.0.3922:sonar -Dsonar.projectKey=sast-demo -Dsonar.projectName=sast-demo -Dsonar.host.url=http://localhost:9000 -Dsonar.token=squ_0d5f324517826d9e7091f343d9b09eb180e1943b'
            }
        }
    }
}
