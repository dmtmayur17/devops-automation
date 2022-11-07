pipeline {
    agent any
  


    stages{
        stage('Git Checkout'){
            steps{
                 timestamps {
                 logstash{ 
                    git credentialsId: 'MyGitHub',branch: 'main', url:'https://github.com/Nithyareddy62/devops-automation.git'
                 }
            }
            }
        }
        stage('Build maven'){
           steps{
                timestamps {
               logstash{ 
               sh 'mvn clean install'
                 }
                }
           }
         }
    }
}
