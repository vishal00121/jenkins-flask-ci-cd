pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/your-username/flask-ci-cd.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'python3 -m venv venv && . venv/bin/activate && pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh '. venv/bin/activate && pytest test_app.py'
            }
        }

        stage('Deploy') {
            steps {
                sh 'nohup . venv/bin/activate && python app.py &'
            }
        }
    }
}
