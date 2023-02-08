pipeline {
    agent any

    stages {
        stage('helm deploy') {
            steps {
                sh 'git clone https://github.com/rituparna1997/mysql-mynginix-lts.git'
                sh 'cd /var/jenkins_home/workspace/mysql-mynginx/mysql-mynginix-lts'
                sh 'ls'
                sh 'helm install my-nginx-mysql /mysql-mynginix-lts'
                
            }
        }
    }
}
