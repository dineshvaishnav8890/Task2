pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t myapp .'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests inside Python Docker container...'
                sh '''
                    docker run --rm -v "$PWD":/app -w /app python:3.9-slim bash -c "
                        pip install --upgrade pip &&
                        pip install -r requirements.txt &&
                        pytest
                    "
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the app...'
                sh 'docker run -d -p 5000:5000 myapp'
            }
        }
    }
}
