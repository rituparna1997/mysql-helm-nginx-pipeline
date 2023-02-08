pipeline {
    agent any

    stages {
        stage('helm deploy') {
            steps {
                sh 'cd /var/lib/jenkins/workspace/'
                sh 'ls'
                sh 'sudo helm install my-nginx-mysql /mysql-mynginix-lts'
                
            }
        }
    }
}
