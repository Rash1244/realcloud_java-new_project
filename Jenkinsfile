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
   deploy adapters: [tomcat9(credentialsId: 'tompsswd', path: '', url: 'http://18.226.186.30:8080/')], contextPath: 'webapp', war: '**/*.war'
            }
        }
    }
}
