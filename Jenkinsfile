pipeline {
    agent any
  


    stages{
        stage('Build Maven'){
            steps{
                git credentialsId: 'MyGitHub', url:'https://github.com/Nithyareddy62/devops-automation.git'
                
            }
        }
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t nithyareddy62/devops-integration .'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
                   withCredentials([string(credentialsId: 'nithyareddy62', variable: 'nithyareddy@62')]) {
                   sh 'docker login -u nithyareddy62 -p ${nithyareddy@62}'

}
                   sh 'docker push nithyareddy62/devops-integration'
                }
            }
        }
        
          
              
                 
              
            
        
    }
}
