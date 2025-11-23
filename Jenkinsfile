pipeline {
    agent any

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
        echo 'Testing..'
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
