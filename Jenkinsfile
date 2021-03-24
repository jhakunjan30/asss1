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
                 withSonarQubeEnv(credentialsId:'sonarserv' ,installationName: 'sonar_server')
                 { 
                     bat "mvn sonar:sonar \-Dsonar.projectKey=first-web-app \-Dsonar.host.url=http://localhost:9000 \-Dsonar.login=cc98ec943425bdab8e30db83330a07b2f2744846 "
                 }
             }
            
             
         
        }
    }
}
