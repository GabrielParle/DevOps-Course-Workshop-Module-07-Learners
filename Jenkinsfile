


pipeline {
    agent any

    stages {
            stage('Build npm') {
            agent {
        docker { image 'node:16.13.1-alpine' }
            }
            
            steps {
                echo 'Building..npm'
                dir('DotnetTemplate.Web'){

                
                sh 'npm install'
                sh 'npm run build'
                }
                echo 'Built successfully'

            }
        }
        stage('Test') {
            agent {
            docker { image 'node:16.13.1-alpine' }
            }
    
            
            steps {
                echo 'Testing..'
                dir('DotnetTemplate.Web'){

                
                sh 'npm t'
                sh 'npm run lint'
                }
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
