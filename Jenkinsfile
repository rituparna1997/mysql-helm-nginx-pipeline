pipeline {
    agent any

    stages {
        stage('checkout public repo') {
            steps {
                sh 'if [ -d "/var/jenkins_home/workspace/mysql-mynginx/mysql-mynginix-lts/.git" ]; then echo "Folder exists"; git clean -fxd; else echo "Folder does not exist"; fi'
                }
            }
        stage('helm deploy') {
            steps {
                sh 'git clone https://github.com/rituparna1997/mysql-mynginix-lts.git'
                sh 'cd /var/jenkins_home/workspace/mysql-mynginx/mysql-mynginix-lts'
                sh 'ls'
                sh 'helm upgrade my-nginx-mysql mysql-mynginix-lts/mysql-mynginix-lts'
            }
        }
    }
