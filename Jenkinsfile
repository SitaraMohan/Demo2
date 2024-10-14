pipeline {
    agent any 

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from Git
                git url: 'https://github.com/SitaraMohan/Demo2.git', branch: 'main' // Change to your repo and branch
            }
        }

        stage('Build') {
            steps {
                // Build the project using Maven
                bat 'clean package' // Use 'bat' for Windows
            }
        }

        stage('Test') {
            steps {
                // Run tests
                bat 'test' // Use 'bat' for Windows
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the application (this is just an example step)
                echo 'Deploying the application...'
                // Add your deployment commands here
            }
        }
    }

    post {
        success {
            echo 'Build and Tests were successful!'
        }
        failure {
            echo 'Build or Tests failed.'
        }
    }
}
