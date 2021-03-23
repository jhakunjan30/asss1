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
        stage('Sonar Code Analysis'){
            def scannerhome = tools 'sonar_scanner'
            withSonarQubeEnv ('sonar_server') {
                bat """C:\Freshers\sonarqube-8.7.1.42226\sonarqube-8.7.1.42226\bin\StartSonar"""
            
            }
        }
    }
}
