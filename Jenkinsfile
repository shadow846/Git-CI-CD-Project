pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/shadow846/Git-CI-CD-Project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t goutham-html-site .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh '''
                        docker stop html-site-container || true
                        docker rm html-site-container || true
                        docker run -d --name html-site-container -p 8081:80 goutham-html-site
                    '''
                }
            }
        }
    }
}
