pipeline {
    agent any
  


    stages{
        stage('Git Checkout'){
            steps{
                git credentialsId: 'MyGitHub',branch: 'main', url:'https://github.com/Nithyareddy62/devops-automation.git'
                
            }
        }
        stage('Build maven'){
           steps{
               sh 'mvn clean install'
                 }
         }
            
        stage('Build docker image'){
            steps{
                script{
                    sh 'docker build -t nithyareddy62/demo .'
                    //sh 'sudo -S docker ps'
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
                   withCredentials([string(credentialsId: 'nithyareddy62', variable: 'nithyareddy')]) {
                   sh 'docker login -u nithyareddy62 -p ${nithyareddy}'

}
                   sh 'docker push nithyareddy62/demo
                }
            }
        }
        
          
              
                 
              
            
        
    }
}
