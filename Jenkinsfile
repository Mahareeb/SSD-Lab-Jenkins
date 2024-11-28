pipeline {
    agent any
    environment {
        // Define flag here if it's supposed to be a constant or set via environment
        FLAG = 'true'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building Project ..'
                // Here you can define commands for your build
            }
        }
        stage('Conditional Test') {
            when {
                expression {
                    return env.FLAG == 'false'  // Ensure this returns a boolean directly
                }
            }
            steps {
                echo 'Testing Project because flag is false'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                // Here you can define commands for your tests
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                // Here you can define commands for your deployment
            }
        }
    }
    post {
        always {
            steps {
                echo 'Post Build Running....'
            }
        }
        failure {
            steps {
                echo 'Post action if the build fails....'
            }
        }
    }
}
