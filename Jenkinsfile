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
                                    bat 'start /min python rest_app.py'
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
                                    bat 'start /min python web_app.py'

                                } catch (err) {
                                    echo "Failed: ${err}"
                                }

                            }

                        }

            }
        }
        stage(' back test ') {
            steps {

                dir('Project\\Testing') {
                    script {
                        try {
                            bat ' python l5_backend_testing.py '
                        } catch (err) {
                            echo "Failed: ${err}"
                        }
                    }
                }
            }
        }
        stage(' front test ') {
            steps {
                dir('Project\\Testing') {
                    script {
                        try {
                            bat ' python l5_frontend_testing.py '
                        } catch (err) {
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
                        dir('Project\\Testing') {
                            bat ' python l5_combined_testing.py '
                        }
                    } catch (err) {
                        echo "Failed: ${err}"
                    }
                }
            }
        }
        stage(' finish ') {
            steps {
                script {
                    dir('Project') {
                        bat ' python clean_environemnt.py '
                    }
                }
            }
        }

    }
}
