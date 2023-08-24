pipeline{
    agent any
    environment{
        DIRECTORY_PATH = "github.com"
        TESTING_ENVIRONMENT = "Testing ENV_T1"
        PRODUCTION_ENVIRONMENT = "Production ENV_P2"
    }
    stages{
        stage('Build'){
            steps{
                echo "Fetch the source code from the directory path: ${DIRECTORY_PATH}"
                echo "Compile the code and generate any necessary artifacts"
            }
        }
        stage('Test'){
            steps{
                echo "Unit tests"
                echo "Integration tests"
            }
        }
        stage('Code'){
            steps{
                echo "Check the quality of the code"
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploy the application to a testing environment using Eviroment Variable: ${TESTING_ENVIRONMENT}"
            }
        }
        stage('Approval'){
            steps{
                sleep time: 10, unit: 'SECONDS'
            }
        }
        stage('Deploy to Production'){
            steps{
                echo "Deploy the code to a production environment using Eviroment Variable: ${PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}