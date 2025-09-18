pipeline {
    agent any
    environment {
        ENV_URL = 'pipeline.google.com'
        SSH_CRED = credentials('SSH_CRED') 
}

    parameters {
        string defaultValue: 'myapp', description: 'Application Name', name: 'APP_NAME'
  
}

    stages {
        stage('Hello') {
            steps {
                sh '''
                    echo Hello World
                    echo URL is $ENV_URL
                    env | grep SSH_CRED
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
                echo "Hello Third stage"
                echo "Application Name: ${params.APP_NAME}"
            }
        }
    }
}
