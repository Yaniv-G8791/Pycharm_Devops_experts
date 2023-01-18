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
			            dir('your-sub-directory') {
                			sh "pwd"
           						 }
                    }
                }

                stage('back') {
                    steps {
                        bat 'python rest_app.py'
                        bat 'python backend_testing.py'
                        
                    
                    }
					}
                stage('front') {
                    steps {
                        bat 'python web_app.py'
                        bat 'python frontend _testing.py'

				}}
                
            
			stage('combined'){
				 steps {
				bat 'python combined_testing.py'
				}
			}
			stage('finish'){
				 steps {
				    bat 'python clean_environemnt.py'
						}
			}
        
    }
}
