pipeline {
    agent any

     stages {
        stage('Checkout') {
            steps {
                // Checkout code from SCM
                git url: 'https://github.com/SitaraMohan/Demo2.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                // Compile and package the application
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                // Run unit tests
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the application (this can be customized based on your deployment method)
                echo 'Deploying application...'
                // For example, you might use SCP to copy to a server or use a Docker command
            }
        }
    }

    post {
        success {
            echo 'Build and tests passed!'
        }
        failure {
            echo 'Build or tests failed.'
        }
        always {
            // Archive the artifacts regardless of success or failure
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}
