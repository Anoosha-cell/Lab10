pipeline {
    agent any

    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run Test stage?')
        booleanParam(name: 'deploy', defaultValue: false, description: 'Deploy code?')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
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
                expression { params.deploy == true } // Only deploy if parameter is true
            }
            steps {
                echo 'Deploying application...'
                // Example deployment command:
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
