#!/usr/bin/env groovy
node('build_node_1') {
  stage('code_checkout') {
    cleanWS()
    checkout scm
  }
  stage('build') {
    mvn clean package
  }
}
