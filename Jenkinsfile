pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git branch: 'main', url: 'https://github.com/piyushpingle55/pythonhelloworld.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    echo 'Next step is Docker Image to be build'
                    dockerImage = docker.build('python-hello-world')
                    echo 'Docker Image build successful'
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    dockerImage.run()
                    echo 'Container created'
                }
            }
        }
    }
}
