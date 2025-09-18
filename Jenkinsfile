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
                    echo URL is $ENV_URL
                '''
            }
        }
        stage('Bye World') {
            environment {
                STAGE_URL = 'stage.google.com'
            }
            steps {
                sh '''
                    echo Bye World
                    echo Stage URL is $STAGE_URL
                '''

            }
        }
        stage('Thrid stage') {
            steps {
                echo 'Hello Third stage'
            }
        }
    }
}
