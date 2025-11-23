pipeline {
    agent any

    // 1️⃣ Add tools here, directly under pipeline
    tools {
        maven 'Maven' // This must match the name of Maven installation in Jenkins
    }

    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run Test stage?')
        booleanParam(name: 'deploy', defaultValue: false, description: 'Deploy code?')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // For Windows use bat, for Linux/Mac use sh
                bat 'mvn -version' // Verify Maven
                // bat 'mvn clean install'  <-- actual build command
            }
        }

        stage('Test') {
            when {
                expression { params.executeTests == true }
            }
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            when {
                expression { params.deploy == true }
            }
            steps {
                echo 'Deploying application...'
            }
        }
    }

    post {
        always {
            echo 'Pipeline Completed'
        }
    }
}
