pipeline {
    agent any

    stages {
        stage('helm deploy') {
            steps {
                sh 'cd /var/jenkins_home/workspace/mysql-mynginx'
                sh 'ls'
                sh 'sudo helm install my-nginx-mysql /mysql-mynginix-lts'
                
            }
        }
    }
}
