node {
    stage('Git Checkout') {
        
        git branch: 'main', credentialsId: 'Github', url: 'https://github.com/abhishekishor/maven-project.git'
        
        echo "=======================================Pulled Code from Github======================================="
        
    }
    
    echo "=========================================Building Maven Project=========================================="
    
    stage('Maven Build') {
        
        def MavenHome= tool name: "Maven-Tool", type: "maven"
        
        def mavenCMD= "${MavenHome}/bin/mvn"
        
        sh "${mavenCMD} clean package"
        
    echo "==========================================Built Maven Project============================================"
    
    echo "=========================================Archieving Artifact============================================="
    
        archiveArtifacts artifacts: '**/*.war'
    
    echo "==========================================Artifact Archieved============================================="
        
    }
      
}
