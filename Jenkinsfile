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
        
        stage('Test on Windows') {
            agent {
                label 'Wind_ows'
            }
            steps {
                sh 'ls'
                sh 'pwd'
            }
            
    }
   }
}
