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
                script {
                    withCredentials([string(credentialsId: '11c8a86f-2480-47fd-bc75-2e8d3482aab0', variable: 'AWS_AMI')]) {
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