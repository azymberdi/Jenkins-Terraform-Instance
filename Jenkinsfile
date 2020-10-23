pipeline {
    agent any
    tools {
        "org.jenkinsci.plugins.terraform.TerraformInstallation" "terraform-0.11.8"
    }


    stages {
      stage('fetch_latest_code') {
        steps {
          git credentialsId: 'GitHub-Creds', url: 'https://github.com/azymberdi/Jenkins-Terraform-Instance'
        }
      }

      stage('TF Init&Plan') {
        steps {
          sh 'terraform init'
          sh 'terraform plan'
        }      
      }

    

      stage('TF Apply') {
        steps {
          sh 'terraform apply -input=false'
        }
      }
    } 
  }
