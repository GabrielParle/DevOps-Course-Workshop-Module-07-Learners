


pipeline {
    agent any

    stages {
            stage('Build npm') {
            agent {
        docker { image 'node:16.13.1-alpine' }
    }
            dir('DotnetTemplate.Web')
            steps {
                echo 'Building..npm'

                
                sh 'npm install'
                sh 'npm run build'
                echo 'Built successfully'

            }
        }
        stage('Test') {
            dir('DotnetTemplate.Web')
            steps {
                echo 'Testing..'

                
                sh 'npm t'
                sh 'npm run lint'
            }
        }
        stage('build .NET') {
                     steps {
                           echo 'building .net'
                           sh 'dotnet build'
                           }
                           }
         stage('.net test') {
                     steps {
                           echo 'tets .net'
                           sh 'dotnet test'
                           }
                           }


    }
}
