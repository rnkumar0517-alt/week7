pipeline {
    agent any
    
    environment {
        DOCKER_USERNAME = "Nithish Kumar"
        DOCKER_PASSWORD = credentials('Rachakonda@05')
    }

    stages {
        stage('Clone Repo') {
            steps {
                git url: 'https://github.com/rnkumar0517-alt/week7.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t week7-app:latest .'
            }
        }

        stage('Docker Login') {
            steps {
                sh "echo ${Rachakonda@05} | docker login -u ${Nithish Kumar} --password-stdin"
            }
        }

        stage('Tag & Push Image') {
            steps {
                sh 'docker tag week7-app:latest ${Nithish Kumar}/week7-app:latest'
                sh 'docker push ${Nithish Kumar}/week7-app:latest'
            }
        }
    }
}
