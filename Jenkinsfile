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
                sh 'docker build -t my-html-site .'
            }
        }

        stage('Run Docker Container') {
            steps {
                // Stop any running container named html-site
                sh 'docker rm -f html-site || true'

                // Run a fresh one on port 8081
                sh 'docker run -d -p 8081:80 --name html-site my-html-site'
            }
        }
    }
}

