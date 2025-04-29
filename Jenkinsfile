pipeline {
    agent any

    tools {
        maven 'Maven'  // This must match the Maven name in Jenkins config
        jdk 'JDK'      // This must match the JDK name in Jenkins config
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/yasasvini2818/MymavenWebApp.git'
            }
        }

        stage('Build WAR') {
            steps {
                sh 'mvn clean package'
            }
        }

    }

    post {
        success {
            echo 'Build and deployment successful.'
        }
        failure {
            echo 'Build or deployment failed.'
        }
    }
}
