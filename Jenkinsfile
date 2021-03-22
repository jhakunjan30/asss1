node{
  stage('SCM Checkout'){
    sh 'git clone https://github.com/jhakunjan30/asss1.git'
  }
  stage('Compile-Package'){
    def MAVEN_HOME = tool name: 'Maven3', type: 'maven'
    sh "${MAVEN_HOME}/bin/mvn package"
  
  }
} 
