#!/usr/bin/env groovy
node('build_node_1') {
  stage('code_checkout') {
    cleanWs()
    checkout scm
  }
  stage('build') {
    steps {
    sh 'mvn -B -DskipTests clean package'
    }
  }
}
