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
            git branch: 'main', poll: false, url: 'https://github.com/AliRizwan1/project-1'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
