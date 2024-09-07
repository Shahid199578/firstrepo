pipeline {
    agent any

    environment {
        // Define the folder where the Git content will be pulled
        FOLDER_NAME = 'develop'
        REPO_URL = ' https://github.com/Shahid199578/firstrepo.git '
        BRANCH_NAME = 'develop'
    }

    stages {
        stage('Checkout') {
            steps {
                script {
                    // Clean up previous workspace
                    deleteDir()

                    // Create a directory for the Git content
                    sh "mkdir -p ${env.FOLDER_NAME}"

                    // Checkout code from Git into the specific folder
                    dir(env.FOLDER_NAME) {
                        git branch: env.BRANCH_NAME, url: env.REPO_URL
                    }
                }
            }
        }
        stage('Build') {
            steps {
                // Build steps here
                echo 'Building...'
            }
        }
        stage('Deploy') {
            steps {
                // Deploy steps here
                echo 'Deploying...'
            }
        }
    }
} 
