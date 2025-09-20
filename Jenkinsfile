pipeline {
    agent {
        label 'Jenkins_Node1'
    }

    stages {
        stage('Build') {
            steps {
                sh '''
                echo "This runs only on the feature1 branch"
                git branch
                '''
            }
        }
    }
}