pipeline 
{
    agent any
    environment {
       TF_VAR_aws_ami="${AWS_AMI}"
    }
    // parameters {
    //     string(name: 'AWS_AMI', defaultValue: 'xxx', description: 'aws ami image',)
    // }

    stages {
        stage('Fetch variables ') {
            steps {
                withCredentials([usernamePassword(credentialsId: '16a63e43-c96e-498d-858c-a68eb5329ad2', passwordVariable: 'AWS_AMI', usernameVariable: 'AWS_AMI')]) 
                {
                script {
                        env.TF_VAR_aws_ami = AWS_AMI
                    }
                }
            }
        }
        stage('Test variables') {
            steps {
                    sh """
                    echo $TF_VAR_aws_ami
                    """
            }
        }
    }
}