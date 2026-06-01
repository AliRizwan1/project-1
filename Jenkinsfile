pipeline {
    agent any

    environment {
        PYTHON = 'python3'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/AliRizwan1/project-1'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                    python3 -m pip install --upgrade pip
                    if [ -f requirements.txt ]; then
                        pip3 install -r requirements.txt
                    fi
                '''
            }
        }

        stage('Run Python Script') {
            steps {
                sh '''
                    python3 main.py
                '''
            }
        }
    }

    post {
        success {
            echo 'Python script executed successfully.'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
