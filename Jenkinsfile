pipeline {
    agent {
        label 'AGENT-1'
    }
    option{
        timeout(time: 0.5, unit: 'HOURS') // Set a timeout for the entire pipeline
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'sleep 10' // Simulate a build step that takes some time
            }
        }

        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }

    post {
        always {
            echo 'This will always run'
            deleteDir() // Clean up the workspace after the build
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
    }
}