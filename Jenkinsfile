// pipeline {
//     agent any

//     stages {
//         stage('Git Checkout') {
//             steps {
//                 script {
//                     echo "Checking out code from Git"
//                     git branch: 'main', url: 'https://github.com/sankalpgunturi/todo.git'
//                 }
//             }
//         }

//         stage('SonarQube Analysis') {
//             steps {
//                 script {
//                     echo "Running SonarQube analysis"
//                     def scannerHome = tool name: 'sonar_scanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
//                     withSonarQubeEnv('sonar-6') {
//                         sh "${scannerHome}/bin/sonar-scanner"
//                     }
//                 }
//             }
//         }
//     }
// }
pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                script {
                    echo "Checking out code from Git"
                    git branch: 'main', url: 'https://github.com/sankalpgunturi/todo.git'
                }
            }
        }

        stage('SonarQube Analysis') {
            steps {
                script {
                    echo "Running SonarQube analysis"
                    def scannerHome = tool name: 'sonar_scanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
                    withSonarQubeEnv(credentialsId: 'sonarqube-credentials') {
                        sh "${scannerHome}/bin/sonar-scanner"
                    }
                }
            }
        }
    }
}
