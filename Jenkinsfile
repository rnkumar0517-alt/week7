pipeline {
    agent any
    
    environment {
        DOCKER_USERNAME = "nithish0517"
        DOCKER_PASSWORD = credentials('rachakonda05')
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
                sh "echo ${rachakonda05} | docker login -u ${nithish0517} --password-stdin"
            }
        }

        stage('Tag & Push Image') {
            steps {
                sh 'docker tag week7-app:latest ${nithish0517}/week7-app:latest'
                sh 'docker push ${nithish0517}/week7-app:latest'
            }
        }
    }
}
