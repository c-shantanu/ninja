Assignment 4:
Create a Declarative CI pipeline for java based project that contains various stages like
Code checkout
Run below stages in parallel
- Code stability.
- Code quality analysis.
- Code coverage analysis.
Generate a report for code quality & analysis.
Publish artifacts.
Send Slack and Email notifications.
The user should have the option to skip various scans in the build execution. And before publish there should be an approval stage to be set in place to approve or deny the publish and if approved the step should execute and the user should be notified post successful/failed
Repeat the same using Scripted Pipeline.


#Declarative Pipeline Script
pipeline {
    agent any
    tools {
        maven 'mvn'
    }

    stages {
        stage('Declarative CI Pipeline') {
            steps {
                echo 'This is Declarative Pipeline'
            }
        }
        stage('Code Checkout') {
            steps {
                echo 'Started Cloning'
                git 'https://github.com/OT-MyGurukulam/spring3hibernate.git'
            }
        }
        stage('Parallel Phase') {
            parallel {
                stage('Code Stability') {
                    steps {
                        echo "Testing code stability"
                        sh 'mvn test'
                    }
                }
                stage('Code Quality Analysis') {
                    steps {
                        echo "Check code quality using PMD"
                        sh 'mvn pmd:pmd'
                    }
                }
                stage('Code Coverage Analysis') {
                    steps {
                        echo "Check code coverage analysis using Jacoco"
                        sh 'mvn clean verify'
                    }
                }
            }
        }
        stage('Approval') {
            steps {
                input message: 'Do you want to proceed with publishing?', ok: 'Approve'
            }
        }
        stage('Publish Artifacts') {
            steps {
                echo 'Start to publish artifact'
                sh 'mvn package'
            }
        }
    }
    
    post {
        success {
            script {
                emailext body: 'Job Succesfully Done', subject: 'Status of job', to: 'itsmeshantanuchauhan@gmail.com'
                slackSend channel: 'jenkins_notification_ninja23', message: 'Job run successfully'
            }
        }
        failure {
            script {
                emailext body: 'Job failed', subject: 'Status of job', to: 'itsmeshantanuchauhan@gmail.com'
                slackSend channel: 'jenkins_notification_ninja23', message: 'Job failed'
            }
        }
    }
}

![Screenshot 2023-10-26 at 11 16 29 PM](https://github.com/c-shantanu/ninja/assets/52127255/b02c56bf-9fd6-45d0-84d8-ac17556f382b)

