pipeline
{
    agent any
    stages {
        stage (git) {
            steps {
                git branch: 'main', url: 'https://github.com/vamsibyramala/live01.git'
            }
        }
        stage (maven) {
            steps {
                sh 'mvn clean package'
            }
        }
        stage (deploy) {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://65.1.135.128:8080/')], contextPath: 'ROOT', war: '**/*.war'
            }
        }
    }
}
