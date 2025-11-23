pipeline {
    agent any

    // 1️⃣ Add Parameters before stages
    parameters {
        booleanParam(name: 'executeTests', defaultValue: true, description: 'Run Test stage?')
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            // 2️⃣ Conditional execution based on parameter
            when {
                expression { params.executeTests == true }
            }
            steps {
                echo 'Testing...'
            }
        }
    }

    // 3️⃣ Post block
    post {
        always {
            echo 'Pipeline Completed'
        }
    }
}
