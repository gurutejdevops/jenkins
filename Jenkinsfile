pipeline {
    agent {
        label 'Jenkins_Node1'
    }

    parameters {
        booleanParam defaultValue: true, description: 'Run Tests?', name: 'RUN_TESTS'
    }
    
    stages {
        stage('Build') {
            when {
                expression {param.RUN_TESTS == false}
            }
            steps {
                echo "Tests are running because RUN_TESTS = false"
            }

        }
    }
}