node{
// demo
   stage('SCM Checkout'){
     git 'https://github.com/sankalpgunturi/todo.git'
   }
  stage('SonarQube Analysis') {
    def scannerHome = tool name: 'sonar_scanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation';
    withSonarQubeEnv('sonar-6') {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}

