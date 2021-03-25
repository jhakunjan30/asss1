pipeline {
    agent any 
    tools{
        jdk "JAVA 1.8"
    }
    stages {
        stage('Clean') { 
            steps {
                //
              bat "mvn clean"
            }
        }
        stage('Test') { 
            steps {
                //
              bat "mvn test"
            }
        }
        stage('Package') { 
            steps {
                //
              bat "mvn package -f First-Web-App"
            }
        }
        stage ('Sonar Code Analysis')
        {
             steps{
                 withSonarQubeEnv(credentialsId:'jenkins_sonar' ,installationName: 'sonar_server')
                 { 
                     bat "mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.3.0.1492:sonar"
                 }
             }
            
             
         
        }
    }
}
