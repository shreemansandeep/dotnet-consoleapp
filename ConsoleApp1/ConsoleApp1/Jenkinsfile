pipeline{
  agent any
  
    stages{
      
      stage("Git Checkout"){
        steps{
              git branch: 'main', credentialsId: 'GitID', url: 'https://github.com/shreemansandeep/dotnet-consoleapp.git'
        }
      }
      
      stage("Docker Image Build"){
            steps{
                  sh 'docker image build -t $JOB_NAME:v1.$BUILD_ID .'
                  sh 'docker image tag $JOB_NAME:v1.$BUILD_ID dockersandheep/$JOB_NAME:v1.$BUILD_ID'
            }
            }
      
    }
}
