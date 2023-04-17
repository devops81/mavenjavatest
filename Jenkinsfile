pipeline {
    agent any
    tools {
        maven 'Maven3'
        jdk 'JAVA11'
    }
    stages {
        stage("Tools initialization") {
            steps {
                sh "mvn --version"
                sh "java -version"
            }
        }
        stage("Checkout Code") {
            steps {
                git branch: 'main',
                url: "https://github.com/devops81/mavenjavatest.git"
            }
        }
        stage("Building Application") {
            steps {
               sh "mvn clean install"
            }
            }
            
        stage("JUNIT REPORT") {
            steps {
               junit allowEmptyResults: true, testResults: 'target/surefire-reports/*.xml'
            }
        }
        
           }
        }
