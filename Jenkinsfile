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

        stage('Deployment Process')
        {
            steps {
                sh "export AWS_DEFAULT_REGION=eu-west-1"
                sh "wget -N -c https://raw.githubusercontent.com/warrensbox/terraform-switcher/release/install.sh"
                sh "chmod 755 install.sh"
                sh "./install.sh -b .bin"
                sh ".bin/tfswitch -b .bin/terraform 1.0.0"
                sh '.bin/terraform init'
                sh '.bin/terraform plan'
            }
        }
    }
}