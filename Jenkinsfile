pipeline {
    agent { label 'agent1' }

    environment {
        GOPATH = "${WORKSPACE}/go"
        PATH = "${PATH}:${GOPATH}/bin"
    }

    stages {
        stage('Install Go') {
            steps {
                script {
                    sh 'sudo yum -y install wget'
                    sh 'wget https://go.dev/dl/go1.21.6.linux-amd64.tar.gz'
                    sh 'sudo tar -C /usr/local -xzf go1.21.6.linux-amd64.tar.gz'
                    sh 'sudo rm go1.21.6.linux-amd64.tar.gz'
                    sh 'export PATH=$PATH:/usr/local/go/bin'
                }
            }
        }

        stage('Build Project') {
            steps {
                script {
                    sh 'ls'
                    sh '/usr/local/go/bin/go build main.go'
                }
            }
        }
    }
}
