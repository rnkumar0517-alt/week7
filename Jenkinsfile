pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git url: 'https://github.com/rnkumar0517-alt/week7.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-kube:latest .'
            }
        }

        stage('Docker Login') {
            steps {
                sh "echo Rachakonda@05 | docker login -u Nithish Kumar --password-stdin"
            }
        }

        stage('Push Docker Image') {
            steps {
                sh 'docker tag my-kube:latest Nithish Kumar/my-kube:latest'
                sh 'docker push Nithish Kumar/my-kube:latest'
            }
        }
    }
}
