


pipeline {
    agent any

    stages {
            stage('Build npm') {
            agent {
        docker { image 'node:16.13.1-alpine' }
    }

            steps {
                echo 'Building..npm'

                sh 'cd DotnetTemplate.Web'
                sh 'npm install'
                sh 'npm run build'
                echo 'Built successfully'

            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'

                sh 'cd DotnetTemplate.Web'
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
