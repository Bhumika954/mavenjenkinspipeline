pipeline {
    agent any  // Use any available agent

    tools {
        maven 'Maven'  // Ensure this matches the name configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Bhumika954/mavenjenkinspipeline.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Starting the Maven build...'
                sh 'mvn clean package'  // Run Maven build
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests...'
                sh 'mvn test'  // Run unit tests
            }
        }

        stage('Run Application') {
            steps {
                echo 'Starting the application...'
                sh 'java -jar target/mavennjenkinspipeline-1.0-SNAPSHOT.jar'  // Start the JAR application
            }
        }
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
