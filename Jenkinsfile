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
                bat 'python -m pip install pymysql os signal flask requests json'

            }
        }
        stage('build') {
            steps {
                bat 'cd Project & python rest_app.py'

            }
        }
    }
}
