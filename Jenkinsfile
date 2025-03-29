pipeline {
    agent any

    stages {
        stage('Select Environment') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'main') {
                        load 'deploy/Jenkinsfile.deploy'
                    } else if (env.BRANCH_NAME == 'develop') {
                        load 'backend/Jenkinsfile.backend'
                    } else {
                        load 'frontend/Jenkinsfile.frontend'
                    }
                }
            }
        }
    }
}