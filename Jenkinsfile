pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git credentialsId: 'jenkins-github-key', url: 'git@github.com:priyannshu7497/flask.git', branch: 'main'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                python3 -m venv venv
                bash -c "source venv/bin/activate && pip install -r requirements.txt"
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                bash -c "source venv/bin/activate && pytest"
                '''
            }
        }

        stage('Deploy to Server') {
            steps {
                sh '''
                bash -c "source venv/bin/activate && python3 app.py &"
                '''
            }
        }
    }
}
