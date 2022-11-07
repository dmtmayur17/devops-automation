pipeline {
    agent any
  


    stages{
        stage('Git Checkout'){
            steps{
                 logstash{ 
                    git credentialsId: 'MyGitHub',branch: 'main', url:'https://github.com/Nithyareddy62/devops-automation.git'
                 }
            }
        }
        stage('Build maven'){
           steps{
               logstash{ 
               sh 'mvn clean install'
                 }
           }
         }
            
        stage('Build docker image'){
            steps{
                script{
                    logstash{ 
                    sh 'docker build -t nithyareddy62/demo .'
                    //sh 'sudo -S docker ps'
                    }
                }
            }
        }
        stage('Push image to Hub'){
            steps{
                script{
                    logstash{ 
                   withCredentials([string(credentialsId: 'nithyareddy62', variable: 'nithyareddy')]) {
                   sh 'docker login -u nithyareddy62 -p ${nithyareddy}'
                   }
}
                   sh 'docker push nithyareddy62/demo'
                }
            }
        }
        
     
    }
}
