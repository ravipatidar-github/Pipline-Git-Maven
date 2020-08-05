pipeline{
    agent any
    tools {
         'Maven 3.6.3', type: 'maven'
    }
    stages{
        stage('compile stage') {
              steps {
                  bat "mvn clean install"
                  
              }
           }
              stage('Testing stage') {
              steps {
                  bat "mvn test"
                  
              }
           }
               stage('build & sonarqube analysis') {
              steps {
                  withSonarQubeEnv('sonarqube')
                  bat 'mvn clean install sonar: sonar'
              }
      }
    }
