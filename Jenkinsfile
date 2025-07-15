pipeline {
    agent any

    stages {
        stage('Pull Code from GitHub') {
            steps {
                git 'https://github.com/shadow846/Git-CI-CD-Project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('goutham-html-site')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    // Stop and remove any old container if running
                    sh '''
                        docker stop html-site-container || true
                        docker rm html-site-container || true
                    '''
                    // Run new container
                    sh 'docker run -d --name html-site-container -p 8081:80 goutham-html-site'
                }
            }
        }
    }
}
