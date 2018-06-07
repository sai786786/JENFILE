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
               nexusArtifactUploader artifacts: [[artifactId: '$BUILD_TIMESTAMP', classifier: '', file: './dist.zip', type: 'zip']], credentialsId: '1eab6339-9825-4a34-ade5-69e0e1a556ed', groupId: 'Dev', nexusUrl: '192.168.1.91:8082', nexusVersion: 'nexus3', protocol: 'http', repository: 'Environments', version: '$BUILD_ID'
      }
      }
        
        /*stage('Test on Windows') {
            agent {
                label 'Avi'
            }
            steps {
                sh 'npm install'
            }
            
    }*/
   }
}
