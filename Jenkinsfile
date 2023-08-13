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
               deploy adapters: [tomcat9(path: '', url: 'http://3.14.132.16:8080/')], contextPath: 'webapp', war: '**/*.war'
            }
        }
    }
}
