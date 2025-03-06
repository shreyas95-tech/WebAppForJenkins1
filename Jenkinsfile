pipeline {
    agent any  // Runs on any available agent (node)

    environment {
        MAVEN_HOME = tool name: 'Maven 3.6.3', type: 'ToolLocation'  // Ensure Maven 3.6.3 is set up in Jenkins tool configuration
        PATH = "${MAVEN_HOME}/bin:${env.PATH}"  // Add Maven to the PATH
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the GitHub repository
                git 'https://github.com/your-username/your-repository.git' // Replace with your repository URL
            }
        }
        
        stage('Build') {
            steps {
                // Run Maven to build the project
                sh 'mvn clean install'  // Maven build command
            }
        }
        
        stage('Test') {
            steps {
                // Run unit tests (optional, depends on your project)
                sh 'mvn test'  // Run tests using Maven
            }
        }
    }

    post {
        always {
            // Clean up actions (if needed)
            echo 'Cleaning up...'
        }
        success {
            // Actions to perform on successful pipeline run
            echo 'Pipeline succeeded!'
        }
        failure {
            // Actions to perform on failed pipeline run
            echo 'Pipeline failed.'
        }
    }
}
