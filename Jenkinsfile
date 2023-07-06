pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        // Checkout your code from version control system
        git url: 'https://github.com/Shahid199578/firstrepo.git'
      }
    }
    
    stage('Build and Package') {
      steps {
        // Build and package your Maven project
        sh 'mvn clean package'
      }
    }

    stage('Deploy to Tomcat') {
      steps {
        // Copy the generated WAR file to the Tomcat webapps directory
        sh 'sudo cp target/*.war /opt/apache-tomcat-9.0.76/webapps'
      }
    }

    stage('Restart Tomcat') {
      steps {
        // Restart the Tomcat server to apply the changes
        sh 'sudo /opt/apache-tomcat-9.0.76/bin/shutdown.sh'
        sleep 5
        sh 'sudo /opt/apache-tomcat-9.0.76/bin/startup.sh'
      }
    }
  }
}
