pipeline{
    agent any
    environment{
        DIRECTORY_PATH = "github.com"
        TESTING_ENVIRONMENT = "Testing ENV_T1"
        PRODUCTION_ENVIRONMENT = "Production ENV_P2"
        STAGING_ENVIRONMENT = "STAGING ENV_ST3"
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
            post {
                always {
                    emailext subject: "Jenkins Build ${currentBuild.currentResult}: Job ${env.JOB_NAME}",
                    body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}",
                    attachLog: true,
                    to: 'chaosktestsof@gmail.com'
                }
            }
        }
        stage('Code'){
            steps{
                echo "Check the quality of the code"
            }
        }
        stage('Security Scan'){
            steps{
                echo "Perform a Security scan"
            }
            post {
                always {
                    emailext subject: "Jenkins Build ${currentBuild.currentResult}: Job ${env.JOB_NAME}",
                    body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}",
                    attachLog: true,
                    to: 'chaosktestsof@gmail.com'
                }
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploy the application to a testing environment using Eviroment Variable: ${TESTING_ENVIRONMENT}"
            }
        }
        stage('Integration Tests'){
            steps{
                echo "Run integration tests on the staging environment: ${STAGING_ENVIRONMENT}"
            }
            post {
                always {
                    emailext subject: "Jenkins Build ${currentBuild.currentResult}: Job ${env.JOB_NAME}",
                    body: "${currentBuild.currentResult}: Job ${env.JOB_NAME} build ${env.BUILD_NUMBER}\n More info at: ${env.BUILD_URL}",
                    attachLog: true,
                    to: 'chaosktestsof@gmail.com'
                }
            }
        }
        stage('Deploy to Production'){
            steps{
                echo "Deploy the code to a production environment using Eviroment Variable: ${PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}
