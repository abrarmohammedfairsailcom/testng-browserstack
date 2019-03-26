pipeline {

    agent any

    stages {

        stage('E2E Tests on Browserstack') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '1564f87f-394c-454f-b4da-21b073f177d1', url: 'https://github.com/abrarmohammedfairsailcom/testng-browserstack']]])
                script {
                    echo "Running E2E Tests on Browserstack"
                    bat 'mvn test -P single'
                }
            }
            /*post {
                always {
                    //step([$class: 'Publisher', showFailedBuilds: true])
                    junit testDataPublishers: [[$class: 'AutomateTestDataPublisher']], testResults: 'target/surefire-reports/TEST-*.xml'
                }
            }*/
        }

        /*stage('Embed Browserstack report') {
            steps{
                script{
                    junit testDataPublishers: [[$class: 'AutomateTestDataPublisher']], testResults: 'target/surefire-reports/TEST-*.xml'
                }
            }

        }*/
    }

    stage('Embed Browserstack report') {
        steps {
            script {
                junit testDataPublishers: [[$class: 'AutomateTestDataPublisher']], testResults: 'target/surefire-reports/TEST-*.xml'
            }
        }

    }
}

