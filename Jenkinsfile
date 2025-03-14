pipeline {
    agent any

//    stages {
//        stage('Clone Repository') {
//            steps {
//                checkout([$class: 'GitSCM', 
//                    branches: [[name: '*/main']], 
//                    userRemoteConfigs: [[url: 'https://github.com/your-repo.git']]
//                ])
//            }
//        }

        stage('Build') {
            steps {
                build 'PES1UG22AM095-1'
                sh 'g++ main.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }

