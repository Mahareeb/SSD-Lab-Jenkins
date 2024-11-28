pipeline {
    agent any
    parameters {
        string(name: 'VERSION', defaultValue: '', description: 'Version to deploy on prod')
        choice(name: 'VERSION_CHOICES', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'Choose version')
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Execute tests')
    }
    environment {
        // Use parameters in the environment section
        NEW_VERSION = "${params.VERSION_CHOICES}"
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo "Building version ${NEW_VERSION}"
            }
        }
        stage('Test') {
            when {
                expression {
                    return params.executeTests
                }
            }
            steps {
                echo 'Testing..'
                echo 'Testing Project'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
                echo "Deploying version ${NEW_VERSION}"
            }
        }
    }
    post {
        always {
            echo 'Post Build Running....'
        }
        failure {
            echo 'Post action if the build fails....'
        }
    }
}
