pipeline {
    agent any

    stages {
        stage('GIT') {
            steps {
                // Checkout code from GitHub
                git branch: 'main',
                    url: 'https://github.com/MaramRezgui1/student-management',
                    credentialsId: 'jenkins-example-github-pat'
            }
        }

        stage('Build') {
            steps {
                // Make Maven wrapper executable
                sh 'chmod +x mvnw'

                // Run the build
                sh 'mvn clean install -DskipTests'
            }
        }

    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}