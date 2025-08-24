pipeline{
    agent {
        label 'AGENT-1'
    }
    options{
        timeout(time: 30 , unit: 'MINUTES')
        disableConcurrentBuilds()
        ansiColor('xterm')
    }
    parameters{
            choice(name: 'CHOICE', choices: ['Apply', 'Destroy'], description: 'Pick something')

    }
    stages{
        stage('init'){
            steps{
                sh """
                    cd 01-VPC
                    terraform init -reconfigure
                """
            }
        }
        stage('plan'){
            steps{
                sh """
                    cd 01-VPC
                    terraform plan
                
                """
            }
        }
        stage('apply'){
            input{
                message "should we continue?"
                ok "Yes, we Should."
            }
            steps{
                sh """
                    cd 01-VPC
                    terraform apply -auto-approve
                
                """
            }
        }
        stage('destroy'){
            steps{
                sh """
                
                
                """
            }
        }
    }
    post{
        always{
            echo 'I will run always'
            deleteDir()
        }
        failure { 
            echo 'I will run when the build failed!'
        }
        success { 
            echo 'I will run when build is success!'
        }
    }

}