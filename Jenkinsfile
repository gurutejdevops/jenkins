pipeline {
    agent any
    environment {
        ENV_URL = 'pipeline.google.com'
        SSH_CRED = credentials('SSH_CRED') 
}

    parameters {
        string defaultValue: 'myapp', description: 'Application Name', name: 'APP_NAME'
        choice(name: 'DEPLOY_ENV', choices: ['dev', 'stage', 'prod'], description: 'Select deployment environment')
  
}

    tools {
        maven 'maven-3.8.6'
        }

    // triggers {
    //     cron '*/2 * * * *'
    // }

    stages {
        stage('Hello') {
            steps {
                sh '''
                    echo Hello World
                    echo URL is $ENV_URL
                    env | grep SSH_CRED
                    mvn -v
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
                echo "Deployment Environment: ${params.DEPLOY_ENV}"
            }
        }
        stage('Password') {
            
            steps {
                withCredentials([usernameColonPassword(credentialsId: 'SSH_CRED', variable: 'Username')]) {
                    sh '''
                        echo "Username is $Username"
                    '''
                    }
            }
        }
    }
}
