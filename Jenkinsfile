pipeline {
    agent any
    triggers {
        githubPush()
    }
    stages {
        stage('Restore packages'){
           steps{
               sh 'dotnet restore testing.sln'
            }
         }
        stage('Clean'){
           steps{
               sh 'dotnet clean testing.sln --configuration Release'
            }
         }
        stage('Build'){
           steps{
               sh 'dotnet build testing.sln --configuration Release --no-restore'
            }
         }
        stage('Publish'){
             steps{
               sh 'dotnet publish testing/testing.csproj --configuration Release --no-restore'
             }
        }
    }
}
