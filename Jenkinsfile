pipeline {
  agent any

  stages {

    stages {
        stage ('Copy source') {
          steps {
            git 'https://github.com/afanaskin/hello.git'
          }
        }

    stage('Terraform') {
      steps {
        sh 'terraform init terraform/'
        sh 'terraform apply --auto-approve terraform/'
          }
        }
      }
}