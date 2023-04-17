pipeline {
    agent any
    tools {
        maven 'MAVEN3'
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
                git branch: 'master',
                url: "https://github.com/devops81/mavenjavatest.git"
            }
        }
        stage("Building Application") {
            steps {
               sh "mvn clean install"
            }
        }
        
           }
        }
