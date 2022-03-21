pipeline {
  agent any

  stages {
    stage ('Copy source') {
      steps {
            git 'https://github.com/afanaskin/sert.git'
      }
    }

    stage('Terraform1') {
      steps {
        sh 'terraform -chdir=terraform/ init'
        sh 'terraform -chdir=terraform/ apply --auto-approve'
      }
    }

    stage('Ansible') {
      steps {
        retry(count: 5) {
        sh 'ansible-playbook -i /etc/ansible/aws_ec2.yml ansible/provisioning.yml --vault-password-file /var/lib/jenkins/av_sc'
        }
      }
    }
  }
}