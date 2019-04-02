#!/usr/bin/env groovy
node('build_node_1') {
  stage('code_checkout') {
    cleanWs()
    checkout scm
  }
  stage('SonarQube analysis') {
    // requires SonarQube Scanner 2.8+
    def scannerHome = tool 'SonarQube Scanner 2.8';
    withSonarQubeEnv('mysonar') {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
  stage('build') {
    sh 'echo "PATH = ${PATH}"'
    sh 'echo "M2_HOME = ${M2_HOME}"'  
    sh 'mvn clean package'
  }
  
}
