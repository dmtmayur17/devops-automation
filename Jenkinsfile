pipeline {
    agent any
  


    stages{
        stage('Git Checkout'){
            steps{
                 timestamps {
                    git credentialsId: 'MyGitHub',branch: 'main', url:'https://github.com/Nithyareddy62/devops-automation.git'
                    logstashSend failBuild: true, maxLines: 1000
                 }
            
            }
        }
        stage('Build maven'){
           steps{
                timestamps {
                    sh 'mvn clean install'
                    logstashSend failBuild: true, maxLines: 1000
                 }
                
           }
         }
    }
}
