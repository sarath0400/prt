pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/sarath0400/prt.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t prt-app .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f prt || true'
                sh 'docker run -d -p 8085:80 --name prt prt-app'
            }
        }
    }
}
