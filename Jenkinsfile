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
                    sh 'wget https://golang.org/dl/go1.21.linux-amd64.tar.gz'
                    sh 'tar -C /usr/local -xzf go1.21.linux-amd64.tar.gz'
                    sh 'rm go1.21.linux-amd64.tar.gz'
                    sh 'export PATH=$PATH:/usr/local/go/bin'
                }
            }
        }

        stage('Build Project') {
            steps {
                script {
                    sh 'ls'
                    sh 'pwd'
                    sh 'cd && go build'
                }
            }
        }
    }
}
