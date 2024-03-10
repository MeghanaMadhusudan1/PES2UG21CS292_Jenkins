pipeline {
    agent any 
    stages {
        stage('Build'){
            steps {
                // Intentionally failing step
                sh 'exit 1'
                sh 'g++ main.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post{
        failure{
            echo 'Pipeline failed' // Printing the message instead of 'error' for clarity
        }
    }
}
