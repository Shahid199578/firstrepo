pipeline {
    agent any
    tools {
        maven 'mvn'
    }
    stages{
        stage('Git Checkout') {
        
        git branch: 'master', url: 'https://github.com/Shahid199578/firstrepo.git'
    }
        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
        
        stage('Archive Artifact') {
            steps {
                archiveArtifacts 'target/*.war'
            }
        }
}
}
