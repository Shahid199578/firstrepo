node {
    stage('Git Checkout') {
        
        git branch: 'master', url: 'https://github.com/Shahid199578/firstrepo.git'
    }
    stage('Maven Build') {
        
        def MavenHome= tool name: "Maven-Tool", type: "maven"
        
        def mavenCMD= "${MavenHome}/bin/mvn"
        
        sh "${mavenCMD} clean package"
        
    archiveArtifacts artifacts: '**/*.war' 
    }
    stage("push artifact") {
            steps {
                sh "sudo cp **/*.war  /opt/apache-tomcat-9.0.76/webapps"
            }
      
}