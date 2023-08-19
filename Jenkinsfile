pipeline{
    agent any
    tools {
        maven 'Maven'
    }
    stages{
        stage("Test"){
            steps{
                echo "========mvn test========"
                sh "test"
            }
            
        }
        stage("Build"){
            steps{
                sh "mvn package"
                echo "========mvn package========"
            }
            
        }
        stage("Deploy"){
            steps{
                deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://192.168.33.18:8080')], contextPath: '/venkat', war: '**/*.war'
                echo "========Deploy========"
            }
            
        }
    }
    
}
