pipeline{
    agent {
        label 'AGENT-1'
    }
    options{
        timeout(time: 30 , unit: 'MINUTES')
        disableConcurrentBuilds()
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
                
                
                """
            }
        }
        stage('apply'){
            steps{
                sh """
                
                
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

}