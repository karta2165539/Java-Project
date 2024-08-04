pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh """
                pwd
                cd $WORKSPACE/Calculator"
                mvn clean compile
                """
            }
        }
        stage('Test') {
            steps {
                sh "mvn test"
            }
        }
        stage('Deploy') {
            steps {
                sh "mvn package"
            }
        }
    }
}
