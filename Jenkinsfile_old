#!groovy
node('build-node')
{
   stage('checkout')
    {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '91af51ec-e73c-4b5a-b9b0-1b30e147279b', url: 'https://github.com/gagandevappa/hello-world.git']]])
    }
    stage('build')
    {
        withAnt(installation: 'Ant',jdk: 'JDK') {
            env.JAVA_HOME="/usr/lib/jvm/java-8-openjdk-amd64/jre"
            env.PATH = "${JAVA_HOME}/bin/java${tool 'Ant'}/bin:${env.PATH}"
            sh 'cd /root/jenkins/workspace/javaTest/ && ant'
        }
    } 
}
