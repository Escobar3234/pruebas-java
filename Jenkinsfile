pipeline {
    agent { label 'agent2' }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Escobar3234/pruebas-java.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
    }
}