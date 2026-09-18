pipeline{
    agent any

    stages{
        stage('Checkout'){
            steps{
                echo "checking out the source code........."
                checkout sum
            }
        }

        stage("Validate"){
            steps{
                echo "Validate the all files........"
                bat 'dir'
            }
        }

        stage('Build'){
            steps{
                echo "Building docker image...."
                bat 'sudo docker build -t cicd-image:latest .'
            }
        }
    }

    post{
        success{
            echo "CI-CD pipeline is complete successfully:"
        }

        failure {
            echo "CI_CD is not completed successfully"
        }
    }
}