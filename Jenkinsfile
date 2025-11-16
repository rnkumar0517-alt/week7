pipeline {
    agent any

    environment {
        USER_CREDS = credentials('nithish0517')
        PASS_CREDS = credentials('rachakonda05')
    }

    stages {

        stage('Checkout') {
            steps {
                git url: 'https://github.com/rnkumar0517-alt/week7.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t week7-app .'
            }
        }

        stage('Docker Login') {
            steps {
                sh """
                    echo ${PASS_CREDS} | docker login -u ${USER_CREDS_USR} --password-stdin
                """
            }
        }

        stage('Push Docker Image') {
            steps {
                sh "docker tag week7-app ${USER_CREDS_USR}/week7-app:latest"
                sh "docker push ${USER_CREDS_USR}/week7-app:latest"
            }
        }
    }
}
