pipeline {
    agent any
    stages {
        
        stage('Build') {
            steps {
                dir('Calculator') {
                    sh "mvn clean compile"
                }
            }
        }
        stage('Test') {
            steps {
                dir('Calculator') {
                    sh "mvn test"
                }
            }
        }
        stage('Deploy') {
            steps {
                dir('Calculator') {
                    sh "mvn package"
                }
            }
        }
        stage('SonarQube Scan') {
            steps {
                dir('Calculator') {
                    withSonarQubeEnv('MySonarQube') {
                        sh "mvn sonar:sonar"
                    }
                }				
            }
        }	
    }
}
