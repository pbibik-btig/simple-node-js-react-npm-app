pipeline {
  agent any
 
  tools {nodejs "node"}
 
  stages {
      
    stage('Cloning') {
      steps {
        git 'https://github.com/pbibik-btig/simple-node-js-react-npm-app.git'
      }
    }
    
    stage('Install dependencies') {
        steps {
            sh 'npm install'
        }
    }
    
    stage('Deliver') { 
            steps {
                sh './jenkins/scripts/deliver.sh' 
                input message: 'Finished using the web site? (Click "Proceed" to continue)' 
                sh './jenkins/scripts/kill.sh' 
            }
        }
    
  }
}