pipeline {
    agent {
    node {
      label 'master'
    }
}
   
    
    stages {
         stage('Test123') {  
        steps {
               sh 'ls'
               sh 'npm install'
        }
           }
    
        stage('build') {
                          

            steps {
               
               sh 'ng build'
            }
        }
           
        stage('working_group') {  
       
               steps {
        fileOperations([fileZipOperation('./dist')])
        }
    }
           }
        
        stage('Test on Windows') {
            agent {
                label 'Wind_ows'
            }
            steps {
                  sh 'ls'    
                
            }
            
    }
   }
