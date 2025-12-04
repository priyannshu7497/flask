pipeline {
    agent any

    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs()
            }
        }

        stage('Checkout Code') {
            steps {
                git credentialsId: 'jenkins-github-key', url: 'git@github.com:priyannshu7497/flask.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh """
                python3 -m venv venv
                source venv/bin/activate && pip install -r requirements.txt
                """
            }
        }

        stage('Run Tests') {
            steps {
                echo "Running tests..."
            }
        }

        stage('Deploy to Server') {
            steps {
                echo "Deploying..."
            }
        }
    }
}
