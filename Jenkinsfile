node{
  stage('SCM Checkout'){
    git 'https://github.com/jhakunjan30/assignments/new/master/FirstWebApp'
  }
  stage('Compile-Package'){
    def MAVEN_HOME = tool name: 'Maven3', type: 'maven'
    sh "${MAVEN_HOME}/bin/mvn package"
  
  }
}
