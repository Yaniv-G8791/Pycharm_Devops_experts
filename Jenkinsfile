pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                git 'https://github.com/Yaniv-G8791/Pycharm_Devops_experts'
            }
        }
        stage('setup import libs') {
            steps {
                bat 'python -m pip install pymysql flask'

            }
        }
        stage('build') {
            steps {
                bat 'cd Project'
                bat 'python rest_app.py'
                bat 'python web_app.py'
                bat 'backend_testing.py'
                bat 'frontend _testing.py'
                bat 'combined_testing.py'
                bat 'clean_environemnt.py'
            }
        }
    }
}
