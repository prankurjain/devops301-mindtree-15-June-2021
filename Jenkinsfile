node('master') {
    
    
    stage('CheckOut') {
      git branch: 'main', url: 'https://github.com/amitvashisttech/devops301-mindtree-15-June-2021.git'
    }  
    
  dir('03-App-Code/petclinic-code/') {
    
    stage('Maven-Clean') {
      sh ' mvn clean'
    }
    
    stage('Maven-Compile') {
      sh ' mvn compile'
    }
    
    stage('Maven-Test') {
      sh ' mvn test'
    }
    
    stage('Maven-Package') {
      sh ' mvn package'
    }  
    
    stage('Archive Artifact') {
      archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
    }  
    
    stage('Docker Deployment') {
      sh 'docker-compose up -d --build'
    }  
    
    
  }
    
    
    
}
