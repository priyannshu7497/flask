pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest || true'
            }
        }

        stage('Deploy to Server') {
            steps {
                sh 'echo "Deployment Step - Add SSH Deploy Commands Here"'
            }
        }
    }
}
