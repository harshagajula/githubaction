pipeline {
    agent any
    stages {
        stage (scm) {
            steps {
                git branch: 'main', url: 'https://github.com/vinodbangaru/live01.git'
            }
        }
        stage (maven) {
            steps {
                sh 'mvn clean package'
            }
        }
        stage (deploy) {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://43.205.229.18:8081/')], contextPath: 'vinod', war: '**/*.war'
            }
        }
    }
}
