#!groovy

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                try{
                    bat 'C:\ProgramData\NuGet\nuget.exe restore /HelloWorld/HelloWorld.sln'
		            bat "\"${tool 'MSBuild'}\" /HelloWorld/HelloWorld.sln /p:Configuration=Release /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"
                }catch(error){
                    throw error
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}