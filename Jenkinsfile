pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git 'https://github.com/priyanshu7497/flask.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'pytest || true'
            }
        }

        stage('Deploy to Server') {
            steps {
                sh "ssh -o StrictHostKeyChecking=no ubuntu@13.60.16.94 'cd /var/www/flask && git pull && sudo systemctl restart flaskapp'"
            }
        }
    }
}
