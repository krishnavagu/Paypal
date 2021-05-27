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
                deploy adapters: [tomcat9(credentialsId: 'Deployment', path: '', url: 'http://54.82.62.22:8089/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
