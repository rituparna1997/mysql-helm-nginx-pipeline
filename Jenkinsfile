pipeline {
    agent any

    stages {
        stage('checkout public repo') {
            steps {
                sh 'if [ -d "/var/jenkins_home/workspace/mysql-mynginx/mysql-mynginix-lts/.git" ]; then echo "Folder exists"; rm -rf /var/jenkins_home/workspace/mysql-mynginx/mysql-mynginix-lts; else echo "Folder does not exist"; fi'
                }
            }
        stage('helm deploy') {
            steps {
                script {
                    sh 'git clone https://github.com/rituparna1997/mysql-mynginix-lts.git'
                    def chartName = "my-nginx-mysql"
                    def result = sh(script: "helm ls -n devops-tools | grep '\${chartName}' | awk '{print \$1}'", returnStdout: true).trim()
                    if (result == chartName) {
                        echo "Chart '${chartName}' is already deployed. Upgrading chart."
                        sh "helm upgrade ${chartName} mysql-mynginix-lts/mysql-mynginix-lts --install"
                    } else {
                        echo "Chart '${chartName}' '${result}' is not deployed. Installing chart."
                        sh "helm install ${chartName} mysql-mynginix-lts/mysql-mynginix-lts"
                    }
                }
            }
        }
    }
}
