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
    }
}