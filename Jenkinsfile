pipeline {
    agent {
    node {
      label 'master'
    }
}
   
    
    stages {
         stage('Test123') {  
        steps {
               sh 'npm install'
        }
           }
    
        stage('Test') {
                          

            steps {
               
                sh 'npm run ng build'
            }
        }
           
        stage('working_group') {  
        steps {
               fileOperations([fileZipOperation('./dist')])
        }
           }
      stage('Uploading Artifact'){
      steps{
               nexusArtifactUploader artifacts: [[artifactId: '$BUILD_TIMESTAMP', classifier: '', file: '/dist.zip', type: 'zip']], credentialsId: 'b8fbf9db-3400-4a8d-9301-221768d5756e', groupId: 'Dev', nexusUrl: '192.168.1.91:8081/nexus', nexusVersion: 'nexus2', protocol: 'http', repository: 'Environment', version: '$BUILD_ID'
      }
      }
        
        stage('Test on Windows') {
            agent {
                label 'Avi'
            }
            steps {
                sh 'npm install'
            }
            
    }
   }
}
