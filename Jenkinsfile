pipeline {
    agent any

    options {
        skipDefaultCheckout(true)
    }

    stages
    {
        stage('Clean Ws')
        {
            steps 
            {
                cleanWs()
                sh "git clone https://github.com/bariseser/terraform.git"
            }
        }

        stage('Terraform')
        {
            steps
            {
                sh "terraform init"
                sh "terraform plan"
            }
        }
    }
}