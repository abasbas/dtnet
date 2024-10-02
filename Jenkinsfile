pipeline{
    agent any
    stages{
        stage('git'){
            steps{
                git branch: 'main', changelog: false, credentialsId: 'eaf4fb5c-c95b-40ec-82e7-7ef3b85a1b5e', poll: false, url: 'git@github.com:abasbas/dtnet.git'
                
            }
        }
        stage('build'){
            steps{
                            sh "dotnet build"

            }
            
        }
        stage('publish'){
         steps{
            sh "dotnet publish"
         }  
        }
        stage('run'){
         steps{
            sh "dotnet run /var/lib/jenkins/workspace/fromgitlab/bin/Release/net8.0/dotnet-storage.dll"
         }  
        }
    }
}