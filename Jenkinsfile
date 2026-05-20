pipeline {
    agent any

    environment {
        AWS_ACCESS_KEY_ID = credentials('aws-jenkins').usr
        AWS_SECRET_ACCESS_KEY = credentials('aws-jenkins').psw
        AWS_DEFAULT_REGION = 'ap-south-1'
    }

    stages {

        stage('Clone Repository') {
            steps {
                git 'https://github.com/sahil9186/Terraform.git'
            }
        }

        stage('Terraform Init') {
            steps {
                sh 'terraform init'
            }
        }

        stage('Terraform Validate') {
            steps {
                sh 'terraform validate'
            }
        }

        stage('Terraform Plan') {
            steps {
                sh 'terraform plan'
            }
        }

        stage('Terraform Apply') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        }
    }
}
