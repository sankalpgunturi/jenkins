node{
// demo
   stage('SCM Checkout'){
     git 'https://github.com/javahometech/my-app'
   }
  stage('SonarQube Analysis') {
    def mvn = tool name: 'sonar_scanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation';
    withSonarQubeEnv('sonar-6') {
      sh "${mvn}/bin/mvn clean verify sonar:sonar -Dsonar.projectKey=test -Dsonar.projectName='test'"
    }
  }
}
