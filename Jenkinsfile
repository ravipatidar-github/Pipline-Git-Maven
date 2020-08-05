pipeline{
    agent any
    tools {
          maven 'mvn'
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
    stage ('Deploy') {
        steps {
           echo "Deploying to stage Environment for more tests"; 
        }
    }     
}
