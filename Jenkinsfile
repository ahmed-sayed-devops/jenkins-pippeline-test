pipeline{
    agent {
        label 'aws-agent'
    }
    stages{
        stage('Build'){
            steps{
                script{
                    echo "Building the project..."
                    mvn clean package
                    // Add your build commands here
                }
            }
        }
        stage('Test'){
            steps{
                script{
                    echo "Running tests..."
                    // Add your test commands here
                }
            }
        }
    }
    post {
  success {
    // One or more steps need to be included within each condition's block.
    slackSend channel: '#ahmed-sayed', message: "Build success - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", teamDomain: 'ahmed-sayedworkspace', tokenCredentialId: 'slack-notification'
  }
  failure {
    // One or more steps need to be included within each condition's block.
    slackSend channel: '#ahmed-sayed', message: "Build failed - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>)", teamDomain: 'ahmed-sayedworkspace', tokenCredentialId: 'slack-notification'
  }
}

}