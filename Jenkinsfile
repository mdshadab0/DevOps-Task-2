pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                echo '🔄 Cloning repository...'
                credentialsId: 'f721d32e-1533-4976-9f2b-bfa373352a84', url: 'https://github.com/mdshadab0/DevOps-Task-2.git'
            }
        }

        stage('Build') {
            steps {
                echo '⚙️ Building the application...'
                sh 'pip install -r requirements.txt'  // Change this if your app isn't Python
            }
        }

        stage('Test') {
            steps {
                echo '✅ Running tests...'
                sh 'pytest'  // Change based on your testing tool
            }
        }

        stage('Build Docker Image') {
            steps {
                echo '🐳 Building Docker image...'
                script {
                    docker.build("myapp")
                }
            }
        }

        stage('Deploy') {
            steps {
                echo '🚀 Deploying the Docker container...'
                script {
                    sh 'docker rm -f myapp-container || true'
                    docker.image("myapp").run("-d -p 5000:5000 --name myapp-container")
                }
            }
        }
    }
}
