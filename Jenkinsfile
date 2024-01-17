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
            deploy adapters: [tomcat9(path: '', url: 'http://18.191.132.165:8080/')], contextPath: 'webapp', war: '**/*.war'
            }
        }
    }
}
