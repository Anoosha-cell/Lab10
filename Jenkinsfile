pipeline {
    agent any

    // 1️⃣ Parameters
    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run Test stage?')
        booleanParam(name: 'deploy', defaultValue: false, description: 'Deploy code?')
    }
    environment {
    VERSION = '1.0.0'
}

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            // 2️⃣ Conditional execution
            when {
                expression { params.executeTests == true }
            }
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            when {
                expression { params.deploy == true } // Only deploy if parameter is true
            }
            steps {
                echo 'Deploying application...'
                // Replace with actual deployment commands, e.g.:
                // sh 'scp -r ./build user@server:/var/www/app'
            }
        }
    }

    post {
        always {
            echo 'Pipeline Completed'
        }
    }
}
