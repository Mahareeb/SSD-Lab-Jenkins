pipeline {
    agent any
    tools { 
        // Specifies that Maven is required in this pipeline
        maven 'Maven' // Ensure 'Maven' matches the name of the Maven installation in your Jenkins configuration
    }
    environment {
        // Define NEW_VERSION here so it can be used by any stage
        NEW_VERSION = '1.3.0'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                // Here you can define commands for your build
                echo "Building version ${NEW_VERSION}"
                // Run Maven to install dependencies or build the project
                sh 'mvn install'
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
            //The conditions here will execute regardless of the result of the build
            echo 'Post Build Running....'
        }
        failure {
            //The conditions here will execute if the build has failed
            echo 'Post action if the build fails....'
        }
    }
}
