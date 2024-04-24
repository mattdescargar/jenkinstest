pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Example: Run Maven build
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Example: Run unit tests
                sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Example: Deploy to a remote server
                sh 'ssh user@server "deploy_script.sh"'
            }
        }
    }

    post {
        success {
            echo 'Build successful!'
            // Example: Send notification on success
            mail to: 'team@example.com', subject: 'Build Success', body: 'The Jenkins build was successful.'
        }
        failure {
            echo 'Build failed!'
            // Example: Send notification on failure
            mail to: 'team@example.com', subject: 'Build Failure', body: 'The Jenkins build failed.'
        }
    }
}
