node{
    stage('Build') {
        try {
            sh'echo "Building the project..."'
        }
        catch (Exception e) {
            echo "Build failed"
            throw e
        }
    }
    stage('Test') {
        if (env.BRANCH_NAME == 'feature') {
            sh'echo "Running tests for feature branch..."'           
        } else {
            sh'echo "Running tests for non-feature branch..."'
        }
    }

}