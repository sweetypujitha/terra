pipeline {
  agent any

  environment {
    AWS_ACCESS_KEY_ID = 'AKIARVSCU7B4B6OTJVV3'
    AWS_SECRET_ACCESS_KEY = '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'
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
