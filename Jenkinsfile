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
                sh "git clone git@github.com:bariseser/terraform.git"
            }
        }
    }
}