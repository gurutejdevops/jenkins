pipeline {
    agent any
    environment {
        ENV_URL = 'pipeline.google.com'
    }

    stages {
        stage('Hello') {
            steps {
                sh '''
                    echo Hello World
                    echo URL is ${ENV_URL}
                '''
            }
        }
        stage('Bye World') {
            steps {
                echo 'Bye World'
            }
        }
    }
}
