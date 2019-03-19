#!/usr/bin/env groovy
node('build_node_1') {
  tools {
    maven 'M3'
  }
  stage('code_checkout') {
    cleanWs()
    checkout scm
  }
  stage('build') {
      sh 'echo "PATH = ${PATH}"'
      sh 'echo "M2_HOME = ${M2_HOME}"'
      sh 'mvn -B -DskipTests clean package'
  }
}
