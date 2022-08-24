pipeline {
  agent any 
  statges {
    stage ('build') {
      script {
        sh 'docker build -t jenkins .'
      }
    }
    stage ('tag') {
      script {
        sh 'docker tag jenkins:latest public.ecr.aws/g8n9i4i6/jenkins:latest'
      }
    }
    stage ('build') {
      script {
        sh 'docker push public.ecr.aws/g8n9i4i6/jenkins:latest'
      }
    }
  }
}
