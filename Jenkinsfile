pipeline {
    agent { 
        label 'agent-core'
    }

    stages {
        stage('intall make') {
            steps {
                sh 'sudo apt update'
                sh 'sudo apt install make'
                sh 'sudo apt install build-essential -y'
            }
        }
        stage('install npm') {
            steps {
                sh 'curl -sL https://deb.nodesource.com/setup_15.x | sudo -E bash - && sudo apt-get install -y nodejs'
                sh 'sudo npm install -g npm'
                sh 'sudo npm install -g @angular/cli'
            }
        }
        stage('download and build repo') {
            steps {
                sh 'rm -rf sopo-ng-project && git clone https://github.com/NikaOrl/sopo-ng-project.git'
                sh 'cd sopo-ng-project && sudo npm install && sudo ng build'
            }
        }
    }
}