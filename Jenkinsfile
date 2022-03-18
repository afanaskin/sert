pipeline {
  agent any

  stages {
    stage ('Copy source') {
      steps {
            git 'https://github.com/afanaskin/sert.git'
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