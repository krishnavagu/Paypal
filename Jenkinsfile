pipeline {
    agent any 
    stages {
        stage('Git SCM') { 
            steps {
               git credentialsId: 'krishnavagu', url: 'https://github.com/krishnavagu/Paypal.git'
            }
        }
        stage('Maven Build ') { 
            steps {
                sh label: '', script: 'mvn clean package'
            }
        }
        stage('Tomcat Deploy') { 
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat-server', path: '', url: 'http://54.82.62.22:8089/manager/html')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
