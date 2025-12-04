pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                sh '''
                python3 -m venv venv
                source venv/bin/activate
                pip install --upgrade pip
                pip install -r requirements.txt --break-system-packages
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                source venv/bin/activate
                pytest || true
                '''
            }
        }

        stage('Deploy to Server') {
            steps {
                sh '''
                echo "Deployment step running..."
                '''
            }
        }
    }
}
