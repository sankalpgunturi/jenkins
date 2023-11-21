pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                script {
                    echo "Checking out code from Git"
                    git branch: 'main', url: 'https://github.com/python/typing_extensions.git'
                }
            }
        }

        stage('SonarQube Create Project') {
            steps {
                script {
                    echo "Creating SonarQube project"
                    def scannerHome = tool name: 'sonar_scanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
                    withSonarQubeEnv() {
                        sh "${scannerHome}/bin/sonar-scanner -X -Dsonar.login=admin -Dsonar.password=admin -Dsonar.projectKey=todo_key -Dsonar.projectName=todo_name -Dsonar.sources=."
                    }
                }
            }
        }

        stage('SonarQube Analysis') {
            steps {
                script {
                    echo "Running SonarQube analysis"
                    def scannerHome = tool name: 'sonar_scanner', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
                    withSonarQubeEnv() {
                        sh "${scannerHome}/bin/sonar-scanner -X -Dsonar.login=admin -Dsonar.password=admin -Dsonar.projectKey=todo_key -Dsonar.projectName=todo_name -Dsonar.sources=."
                    }
                }
            }
        }
    }
}

