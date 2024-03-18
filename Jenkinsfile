pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                sh 'cd SampleWebApp mvn test'
            }
        }
        stage('Build') {
            steps {
                sh 'cd SampleWebApp && mvn clean package'
            }
        }
        
        stage('Deploy to Tomcat') {
            steps {
    deploy adapters: [tomcat9(credentialsId: 'id', path: '', url: 'http://3.147.83.121:8080/'), tomcat9(credentialsId: 'tomcat_ID', path: '', url: 'http://3.147.83.121:8080/')], contextPath: 'webapp', war: '**/*.war'
            }
        }
    }
}
