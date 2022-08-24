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
                 sh 'docker build -t alibaba .'
                }
            }
        }
        stage('Tag'){
            steps {
                 sh 'docker tag alibaba:latest 078591229396.dkr.ecr.us-east-1.amazonaws.com/alibaba:latest'
            }
        }
        stage('Deploy') {
            steps {
                script{
                        sh 'docker push 078591229396.dkr.ecr.us-east-1.amazonaws.com/alibaba:latest'
                        }
                       
                    }
                }
            }
        }

