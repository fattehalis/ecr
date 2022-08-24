pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
         stage('Clone repository') { 
            steps { 
                script{
                checkout scm
                }
            }
        }
        stage('Build') { 
            steps { 
                script{
                 sh 'docker build -t jenkins .'
                }
            }
        }
        stage('Tag'){
            steps {
                 sh 'docker tag jenkins:latest public.ecr.aws/g8n9i4i6/jenkins:latest'
            }
        }
        stage('Deploy') {
            steps {
                script{
                        sh 'docker push public.ecr.aws/g8n9i4i6/jenkins:latest'
                        }
                       
                    }
                }
            }
        }

