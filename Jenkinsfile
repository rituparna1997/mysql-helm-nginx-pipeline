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
                    def chartName = "mysql-mynginix-lts"
                    def result = sh(script: "helm ls | grep '^\\${chartName}' | awk '{print \\$1}'", returnStdout: true).trim()
                    if (result == chartName) {
                        echo "Chart '${chartName}' is already deployed. Upgrading chart."
                        sh "helm upgrade ${chartName} mysql-mynginix-lts/mysql-mynginix-lts --install"
                    } else {
                        echo "Chart '${chartName}' is not deployed. Installing chart."
                        sh "helm install ${chartName} ./your-chart-directory"
                    }
                }
            }
        }
    }
}
