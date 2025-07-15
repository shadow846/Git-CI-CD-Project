  GNU nano 8.3                                                                                       Jenkinsfile
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


