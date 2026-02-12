pipeline {
    agent {
        label 'AGENT-1'
    }
    option {
        timeout(time: 30, unit: 'MINUTES') // Set a timeout for the entire pipeline
        disableConcurrentBuilds() // Prevent concurrent builds of this pipeline
        retry(3) // Retry the pipeline up to 3 times if it fails
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