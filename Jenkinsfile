pipeline {
    agent any
    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/shabbeermca2010/saleor.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t shabbeermca2010/saleor:DEV .'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push shabbeermca2010/saleor:DEV'
            }
        }
    }
}
