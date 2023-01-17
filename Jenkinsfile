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
                bat 'cd project & python rest_app.py'
                bat 'python Project\\web_app.py'
                bat 'python Project\\backend_testing.py'
                bat 'python Project\\frontend _testing.py'
                bat 'python Project\\combined_testing.py'
                bat 'python Project\\clean_environemnt.py'
            }
        }
    }
}
