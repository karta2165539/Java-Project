pipeline {
    agent any
    stages {
        stage('SonarQube Scan') {
            steps {
                withSonarQubeEnv('MySonarQube') {
                    bat "mvn sonar:sonar -Dsonar token=sqa_49ae5ad7cc9ef7f272a7af8cb7599889ec4545f2"
                }				
            }
        }	
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
    }
}
