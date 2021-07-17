pipeline {
    agent none
    tools {
        maven 'maven-3'
    }
    parameters{
        string(name:'USERNAME', defaultValue:'', description: 'Enter username ...')
        choice(name:'APP_VERSION', choices:['V1','V2','V3'], description: 'Select application version for deployment')
        booleanParam(name:'EXECUTE_TESTS', defaultValue: true, description: 'Execute Tests ?')
    }
    stages{
        stage('build') {
            steps{
                echo 'building application'
            }
        }
        stage('test') {
            when{
                expression {
                    params.EXECUTE_TESTS == true
                }
            }
            steps{
                echo 'testing application'
            }
        }
        stage('deploy') {
            steps{
                echo 'deploying application'
                echo "application name ${params.APP_VERSION}"
            }
        }
    }
}