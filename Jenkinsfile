pipeline {
    agent {
        docker {
            image 'python:3.9-slim'
        }
    }

    stages {

        stage('Clone Repo') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/your-username/python-jenkins-demo.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                    python --version
                    pip install --no-cache-dir -r requirements.txt || true
                '''
            }
        }

        stage('Run Python Script') {
            steps {
                sh '''
                    python app.py
                '''
            }
        }
    }
}
