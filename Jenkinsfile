pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo '🔧 Building Docker image...'
                    dockerImage = docker.build("my-python-app")
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo '🧪 Running tests inside container...'
                    dockerImage.inside {
                        sh 'python app.py | grep "Hello, Jenkins Pipeline with Docker!"'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo '🚀 Deploying (running container)...'
                    dockerImage.run()
                }
            }
        }
    }
}
