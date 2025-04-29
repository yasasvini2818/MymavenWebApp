pipeline {
    agent any

    tools {
        maven 'Maven'       // Must match name configured in Jenkins
        jdk 'JDK'           // Must match name configured in Jenkins
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
                // Replace with your actual server username, IP, and path
                sh 'scp target/my-webapp.war user@your-server-ip:/path/to/tomcat/webapps/'
            }
        }
    }

    post {
        success {
            echo 'WAR build and deployment completed successfully.'
        }
        failure {
            echo 'Something went wrong during build or deployment.'
        }
    }
}
