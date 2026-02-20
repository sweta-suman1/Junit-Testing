pipeline {
    agent any

    tools {
        maven 'Maven'      // Name configured in Jenkins Global Tool Config
        jdk 'JDK8'        // Name configured in Jenkins
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/your-username/your-repo.git'
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
    }

    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
    }
}
