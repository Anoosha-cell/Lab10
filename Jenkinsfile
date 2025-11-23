pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
    }

    post {
        always {
            echo 'Pipeline Completed'
        }
    }
}
parameters {
    booleanParam(name: 'executeTests', defaultValue: true)
}
