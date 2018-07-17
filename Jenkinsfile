node {
   
   	stage 'Stage 1'
   		echo 'helloworld, shell scripts'
   	stage 'Checkout'
      //GitHub
   		git url: 'https://github.com/github0889/helloworld.git'
      stage ('Code Analysis') {
      //Sonarqube scanner with unit tests
    def scannerHome = tool 'SonarQube Scanner 7.4';
    withSonarQubeEnv('My SonarQube Server') {
      bat "${SONARQUBE_HOME}\bin\windows-x86-64"
        }
      }
pipeline {
    agent { docker 'maven:3.5.4' }
    stages {
        stage('build') {
            steps {
                bat 'mvn --version'
            }
        }
    }
}
