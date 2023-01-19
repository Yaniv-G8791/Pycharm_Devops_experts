pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                git 'https://github.com/Yaniv-G8791/Pycharm_Devops_experts/'
            }

        }
        stage('setup import libs') {
            steps {
                bat 'python -m pip install pymysql flask'

            }
        }

        stage('back') {
            steps {

                dir('Project') {
                    script {
                        try {
                            bat 'python rest_app.py'
                        } catch (err) {
                            echo "Failed: ${err}"
                        }
                    }
                }
            }
        }
        stage('front') {
            steps {
                dir('Project') {
                    script {
                        try {
                            bat 'python web_app.py'

                        }
                        catch (err) {
                        echo "Failed: ${err}"
                    }
                    
                    }

pipeline {
    agent any
    stages {
        stage('checkout') {
            steps {
                git 'https://github.com/Yaniv-G8791/Pycharm_Devops_experts/'
            }

        }
        stage('setup import libs') {
            steps {
                bat 'python -m pip install pymysql flask'

            }
        }

        stage('back') {
            steps {

                dir('Project') {
                    script {
                        try {
                            bat 'python rest_app.py'
                        } catch (err) {
                            echo "Failed: ${err}"
                        }
                    }
                }
            }
        }
        stage('front') {
            steps {
                dir('Project') {
                    script {
                        try {
                            bat 'python web_app.py'

                        }
                        catch (err) {
                        echo "Failed: ${err}"
                    }
                    
                    }

                }
            }
        }
        stage(' back test ') {
            steps {

                dir(' Project ') {
                    script {
                        try {
                            bat ' python backend_testing.py '
                        } catch (err) {
                            echo "Failed: ${err}"
                        }
                    }
                }
            }
        }
        stage(' front test ') {
            steps {
                dir(' Project ') {
                    script {
                        try {
                            bat ' python frontend _testing.py '
                        }
                         catch (err) {
                        echo "Failed: ${err}"
                    }
                   
                    }

                }
            }
        }
        stage(' combined ') {
            steps {
                script {
                    try {
                        dir(' Project ') {
                            bat ' python combined_testing.py '
                        }
                        catch (err) {
                        echo "Failed: ${err}"
                    }
                }
            }
        }
        stage(' finish ') {
            steps {
                script {
                    dir(' Project ') {
                        bat ' python clean_environemnt.py '
                    }
                }
            }
        }
		
}}
}
