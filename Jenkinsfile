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

        stage('Deploy WAR') {
            steps {
                // Replace these values with your actual deployment server
                sh 'scp target/my-webapp.war user@your-server-ip:/path/to/tomcat/webapps/'
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
