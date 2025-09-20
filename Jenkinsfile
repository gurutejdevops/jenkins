pipeline {
    agent {
        label 'Jenkins_Node1'
    }

    environment {
        DEPLOY_ENV = 'dev'
    }
    
    stages {
        stage('Build') {
            when {
                environment name: 'DEPLOY_ENV', value: 'prod'
            }
            steps {
                echo "Deploying to Production"
            }

        }
    }
}