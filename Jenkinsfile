pipeline {
  agent { 
                label 'centos-slave'
            }
            tools {
                maven 'maven'
            }

    stages {
        stage('Hello') {
            steps {
               sh 'mvn --version'
              echo "========executing==========="
            }
        }
      stage('Test') {
            steps {
               sh 'mvn test'
              echo "========executing==========="
            }
        }
       stage('Build') {
            steps {
               sh 'mvn package'
              echo "========executing==========="
            }
        }
        stage('Deploy') {
            steps {
               deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://192.168.33.18:8080')], contextPath: '/venkat', war: '**/*.war'
              echo "========Deployment completed==========="
            }
        }
    }
}
