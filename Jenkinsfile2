pipeline {

    agent any

    /*environment {
        SFDX_USE_GENERIC_UNIX_KEYCHAIN = true

        String sfdx = ""
        String RUN_ARTIFACT_DIR="apexTestResults/${env.BUILD_NUMBER}"
        String FULL_PATH="${env.WORKSPACE}/${env.RUN_ARTIFACT_DIR}"
        //String SFDX_PROJECT_PATH = "./compensation-planning"
        //String FULL_PATH="${env.SFDX_PROJECT_PATH}/${env.RUN_ARTIFACT_DIR}"
        String KKHWTF_TEAMS_URL = "https://outlook.office.com/webhook/3df4b30f-097f-4880-bdb2-dd8e46319bc9@3e32dd7c-41f6-492d-a1a3-c58eb02cf4f8/JenkinsCI/49c0df0a52a847dea60a42a6f2a1f592/f601d12d-ccac-4b18-9db0-d329b8244137"

        SPDEVHUB_CONSUMER_KEY = credentials('sage-people-jenkins-consumer-key')
        SPDEVHUB_USERNAME = credentials('sage-people-jenkins-username')
        SPDEVHUB_JWTKEY = credentials('sage-people-devhub-key')
    }*/

    stages {

        /*stage('sfdx-cli tool setup') {
            steps {
                script {
                    String sfdxtool = tool(
                            name: 'sfdx',
                            type: 'com.cloudbees.jenkins.plugins.customtools.CustomTool'
                    )
                    sfdx = "${sfdxtool}/sfdx"
                }
            }
        }*/

        /*stage('Jasmine Tests') {
            steps {
                withEnv(["PATH+NODE=${WORKSPACE}/web/node_modules/.bin"]) {
                    dir('web') {
                        echo "\n====++++Install/update dependencies++++====\n"
                        sh 'npm ci'

                        echo "\n====++++Running Jasmine tests++++====\n"
                        script {
                            status = sh(
                                    script: 'ng test --watch=false --code-coverage --reporters progress,junit,coverage-istanbul --browsers ChromeHeadless',
                                    returnStatus: true
                            )
                            if (status != 0) {
                                currentBuild.result = 'FAILURE'
                                return
                            }
                        }
                    }
                }

                echo "\n====++++Jasmine test results++++====\n"*/
                //junit '**/*/karma-results.xml'
            /*}

            post {*/
                //Leaving this commented out, as may need in future
                /* success {
                    script {
                        if (env.BRANCH_NAME == 'master') {
                            office365ConnectorSend color: '05b222', message: 'Great job, my beautiful crocodile! :) ', status: 'Success', webhookUrl: '${KKHWTF_TEAMS_URL}'
                        }
                    }
                } */
                /*failure {
                    office365ConnectorSend color: 'd00000', message: 'You are doing garbage! :( ', status: 'Failed', webhookUrl: '${KKHWTF_TEAMS_URL}'
                }
            }
        }*/

        stage('Setting up Environment') {
            /* when {
                anyOf {
                    branch 'master'
                    changeRequest()
                }
            } */
            stages{
                /*stage('Create Scratch Org and Install HCM'){
                    steps {
                        script {
                            echo "\n====++++Authenticating DevHub++++====\n"
                            authDevHub = sh(
                                    returnStatus: true,
                                    script: "${sfdx} force:auth:jwt:grant --clientid ${SPDEVHUB_CONSUMER_KEY} --username ${SPDEVHUB_USERNAME} --jwtkeyfile ${SPDEVHUB_JWTKEY} --setdefaultdevhubusername"
                            )
                            if (authDevHub != 0) {
                                error 'Devhub authorization failed'
                            }

                            echo "\n====++++Create Scratch Org++++====\n"
                            sh "${sfdx} force:org:create --definitionfile project-scratch-def.json --setdefaultusername --durationdays 1"

                            echo "\n====++++Installing HCM Package++++====\n"
                            sh "${sfdx} force:package:install --package 04t1o000000U6T6 --noprompt --wait 60" // HCM 25.5
                        }
                    }
                }*/

                /*stage('Deploy to Scratch') {
                    steps {
                        withEnv(["PATH+NODE=${WORKSPACE}/web/node_modules/.bin"]) {
                            dir('scripts') {
                                echo "====++++Deploying to Scratch Org++++===="
                                sh "./deploy-to-scratch-org"

                            }
                        }
                    }
                }*/

                /*stage('Run Apex Tests') {
                    steps{
                        withEnv(["PATH+NODE=${WORKSPACE}/web/node_modules/.bin"]) {
                            dir('scripts') {
                                script{
                                    echo "\n====++++Install/update dependencies++++====\n"
                                    sh 'npm ci'

                                    echo "\n====++++Run Apex tests++++====\n"
                                    sh "mkdir -p ${RUN_ARTIFACT_DIR}"
                                    sh "./run-apex-tests -d ${RUN_ARTIFACT_DIR}"

                                    *//* runApex = sh(
                                        returnStdout: true,
                                        script: "./run-apex-tests "
                                    )
                                    if (runApex != 0) {
                                        error 'Failed to run Apex tests'
                                    }   *//*
                                }
                            }
                        }
                        post{
                            always{
                                dir("${scripts}") {
                                    echo "\n====++++Apex tests Results++++====\n"*/
                                    //junit "**/${RUN_ARTIFACT_DIR}/*-junit.xml"
                                /*}
                            }
                            success {
                                office365ConnectorSend color: '05b222', message: 'Great job, my beautiful crocodile! :) ', status: 'Success', webhookUrl: '${KKHWTF_TEAMS_URL}'
                            }
                            failure {
                                office365ConnectorSend color: 'd00000', message: 'You are doing garbage! :( ', status: 'Failed', webhookUrl: '${KKHWTF_TEAMS_URL}'
                            }
                        }
                    }
                }*/

                /*stage('REST Tests') {
                    steps {
                        dir('automation') {*/
                            //checkout([$class: 'GitSCM', branches: [[name: '*/compensation_planning']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '1564f87f-394c-454f-b4da-21b073f177d1', url: 'https://github.com/fairsail/wx-automation-test-framework']]])
                            //checkout([$class: 'GitSCM', branches: [[name: '*/cp_abrar']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '1564f87f-394c-454f-b4da-21b073f177d1', url: 'https://github.com/fairsail/wx-automation-test-framework']]])
                            /*script {
                                try {
                                    echo "Running REST Tests"
                                    if (isUnix()) {
                                        sh 'mvn clean install -DskipTests && cd AutomationVerticals/CompensationPlanning && mvn clean test -Dsurefire.suiteXmlFiles=src/test/resources/api_testng.xml'
                                    } else {
                                        bat 'mvn clean install -DskipTests && cd AutomationVerticals\\CompensationPlanning && mvn clean test -Dsurefire.suiteXmlFiles=src\\test\\resources\\api_testng.xml -DreportsDirectory=${project.build.directory}\\apitests\\surefire-reports'
                                    }
                                }catch (err) {
                                    echo "REST Tests failed"
                                }
                            }
                            fileOperations([folderCopyOperation(destinationFolderPath: 'C:\\Users\\DeeptiHarish\\.jenkins\\workspace\\${JOB_NAME}\\AutomationVerticals\\CompensationPlanning\\archive', sourceFolderPath: 'C:\\Users\\DeeptiHarish\\.jenkins\\workspace\\${JOB_NAME}\\AutomationVerticals\\CompensationPlanning\\target')])
                        }
                    }
                    post {
                        always {
                            step([$class: 'Publisher', reportFilenamePattern: 'C:\\Users\\DeeptiHarish\\.jenkins\\workspace\\CP_test_pipeline_Package_cp_Abrar\\AutomationVerticals\\CompensationPlanning\\archive\\surefire-reports\\testng-results.xml'])
                        }
                    }
                }*/

                stage('E2E Tests on Browserstack') {
                    steps {
                        //dir('automation') {
                        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '1564f87f-394c-454f-b4da-21b073f177d1', url: 'https://github.com/abrarmohammedfairsailcom/testng-browserstack']]])
                            script {
                                echo "Running E2E Tests on Browserstack"
                                if (isUnix()) {
                                    //sh 'mvn clean install -DskipTests && cd AutomationVerticals/CompensationPlanning && mvn clean test -Dsurefire.suiteXmlFiles=src/test/resources/ui_testng.xml'
                                } else {
                                    //bat 'mvn clean install -DskipTests && cd AutomationVerticals\\CompensationPlanning && mvn clean test -Dsurefire.suiteXmlFiles=src\\test\\resources\\ui_testng.xml'
                                    bat 'mvn clean compile'
                                    bat 'mvn test -P single'
                                }
                            }
                        //}
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
        }

        stage('Embed Browserstack report') {
            steps{
                script{
                    junit testDataPublishers: [[$class: 'AutomateTestDataPublisher']], testResults: 'target/surefire-reports/TEST-*.xml'
                }
            }

        }
    }
}
