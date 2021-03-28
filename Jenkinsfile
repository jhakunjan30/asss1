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
        
        
        stage('upload to artifactory'){
               
           steps{
      rtUpload (
                    serverId: 'artifactory_server',
                    spec: '''{
                        "files": [
                            {
                            "pattern": "./target/*.war",
                            "target": "example-repo-local"
                            }
                        ]
                    }''',
                    failNoOp: true,
                )
                rtPublishBuildInfo (
                    serverId: 'artifactory_server',
                )
           }
           }
    }
}
