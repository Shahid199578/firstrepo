pipeline {
    agent any
    tools {
        maven 'Maven-Tool'
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Shahid199578/firstrepo.git'
            }
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
        stage("push artifact") {
            steps {
                sh "sudo cp target/*.war  /opt/apache-tomcat-9.0.76/webapps"
            }
        }
    }
}
