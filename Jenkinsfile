pipeline {
  agent any

  environment {
    AWS_ACCESS_KEY_ID = 'AKIAX3SKLMPKWHLZTAVF'
    AWS_SECRET_ACCESS_KEY = 'uZLbweU1G1y8hHi3O/vgjDHF4juZlxD'
    AWS_DEFAULT_REGION = 'us-east-1'
  }

  stages {
    stage('git') {
        steps {
            sh 'git init'
            sh "git pull https://github.com/sweetypujitha/terra.git"
        }
    }
    stage('Terraform Init') {
      steps {
        sh 'terraform init'
      }
    }

    stage('Terraform Plan') {
      steps {
        sh 'terraform plan -out=tfplan'
      }
    }

    stage('Terraform Apply') {
      steps {
        sh 'terraform apply tfplan'
      }
    }
  }
}
