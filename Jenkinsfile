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
                withSonarQubeEnv(installationName: 'sonar-server')
                { 
                    bat "mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar"
                    -Dsonar.login = bc07dd17f004c5e0726ca2319947253241f94a10

 

                }}
            
             
         
        }
    }
}
