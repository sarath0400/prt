pipeline {
    agent any

    stages {

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
