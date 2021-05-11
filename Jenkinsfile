pipeline {
    agent any
    stages {
        stage('git clone') {
            steps {
                git 'https://github.com/mshiekh/maven-app.git'
            }
            
        }
        stage('maven') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('deploy') {
            steps {
                deploy adapters: [tomcat9(credentialsId: 'yeepheee', path: '', url: 'http://54.160.234.251:8181/')], contextPath: 'KTR', war: '**/*.war'
                
            }
        }
        
    }
}
