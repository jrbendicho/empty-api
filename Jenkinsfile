pipeline {
    agent any
    triggers {
        githubPush()
    }
    stages {
        stage('Restore packages'){
           steps{
               sh 'dotnet restore empty-api.sln'
            }
         }
        stage('Clean'){
           steps{
               sh 'dotnet clean empty-api.sln --configuration Release'
            }
         }
        stage('Build'){
           steps{
               sh 'dotnet build empty-api.sln --configuration Release --no-restore'
            }
         }
        stage('Test: Unit Test'){
           steps {
                sh 'dotnet test XUnitTestProject/XUnitTestProject.csproj --configuration Release --no-restore'
             }
          }
        stage('Publish'){
             steps{
               sh 'dotnet publish empty-api/empty-api.csproj --configuration Release --no-restore'
             }
        }
        
    }
}