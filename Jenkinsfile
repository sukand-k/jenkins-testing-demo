pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git'
            }
        }

        stage('Test') {
            steps {
                bat 'python -m pip install --upgrade pip'
                bat 'pip install -r requirements.txt'
                bat 'pytest --junitxml=test-results.xml'
            }
        }
    }

    post {
        always {
            junit 'test-results.xml'
        }
    }
}
