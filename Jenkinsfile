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
                bat 'cd Project & python rest_app.py'

            }
        }
    }
}
