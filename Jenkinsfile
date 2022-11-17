pipeline {
    agent any
  


    stages{
        stage('Git Checkout'){
            steps{
                 timestamps {
                    git credentialsId: 'MyGitHub',branch: 'main', url:'https://github.com/Nithyareddy62/devops-automation.git'
                    logstashSend failBuild: true, maxLines: 10000
                 }
            
            }
        }
        stage('Build maven'){
           steps{
                timestamps {
                    sh 'mvn clean install'
                    echo "Hello From sms"
                    echo $$@
                    logstashSend failBuild: true, maxLines: 10000
                 }
                
           }
         }
    }
        post { 
        always { 
            cleanWs()
            echo "${currentBuild.durationString}"
            currentBuild.result = 'FAILURE'
            echo "${currentBuild.result}"
            logstashSend failBuild: false, maxLines: 10000
        }
    }
    
}
