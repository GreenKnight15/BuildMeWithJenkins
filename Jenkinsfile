#!groovy

pipeline {
    agent any
    def msbuild = tool 'MSBuild'
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                //bat 'C:\ProgramData\NuGet\nuget.exe restore HelloWorld/HelloWorld.sln'
		        bat "\"${msbuild}\" /HelloWorld/HelloWorld.sln /p:Configuration=Release /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"

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