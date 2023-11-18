node{
// demo
   stage('SCM Checkout'){
     git 'https://github.com/javahometech/my-app'
   }
  stage('SonarQube Analysis') {
    def mvn = tool 'sonar-6';
    withSonarQubeEnv() {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=test -Dsonar.projectName='test'"
    }
  }
}
