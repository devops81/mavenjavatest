rtMaven.tool = 'Maven3'
pipeline {
  agent any
  {
    jdk "JAVA11"
    maven "Maven3"
  }
  stages {
    stage('Code Checkout') {
      steps {
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'github', url: 'https://github.com/devops81/mavenjavatest.git']]])
      }
    }

    stage('Build') {
      steps {
        script {
        rtMaven.run pom: 'pom.xml',goals: 'clean install' 
        }
      }
    }

    stage('Notify') {
      steps {
        sh 'echo "This is build notfication step"'
      }
    }

  }
}
