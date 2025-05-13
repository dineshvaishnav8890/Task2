pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t myapp .'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'python3 -m pip install -r requirements.txt'
                sh 'python3 -m unittest discover'
            }
        }

        stage('Deploy') {
            when {
                expression { currentBuild.result == null || currentBuild.result == 'SUCCESS' }
            }
            steps {
                echo 'Deploying application...'
                // Your deploy steps here
            }
        }
    }
}
