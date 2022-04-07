pipeline {
    agent any
    
    environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
        TF_IN_AUTOMATION      = '1'
    }
 
    stages {
         stage('checkout') {
             steps {
        git([url: 'https://github.com/arjunachari12/iac-demo', branch: 'master'])

           }
              
        }
        stage('Terraform Init') {
            steps {
               sh 'terraform init'
            }
        }
         stage('Terraform Apply') {
            steps {
                sh 'terraform apply --auto-approve'
            }
        }
        
        
    }
}
