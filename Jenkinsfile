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
                 withSonarQubeEnv('sonar_server')
                 { 
                     withMaven(maven:'Maven3'){
                        bat 'mvn clean package sonar:sonar'
                     }
                     
                 }
             }
            
             
         
        }
    }
}
