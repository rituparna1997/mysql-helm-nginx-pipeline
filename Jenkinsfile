pipeline {
    agent any

    stages  { 
        stage('checkout public repo'){
            folder = new File("$/var/jenkins_home/workspace/mysql-mynginx/mysql-mynginix-lts/.git")
            if (folder.exists())
            {
               println "Found .git folder. Clearing it.."
               sh'git clean -fxd'
            } 
            checkout scm
        }
        stage('helm deploy') {
            steps
                sh 'git clone https://github.com/rituparna1997/mysql-mynginix-lts.git'
                sh 'cd /var/jenkins_home/workspace/mysql-mynginx/mysql-mynginix-lts'
                sh 'ls'
                sh 'helm upgrade my-nginx-mysql mysql-mynginix-lts/mysql-mynginix-lts/'
                
            }
        }
    }
