pipeline{
    agent any
    stages{
        stage("maven test"){
            steps{
                echo "========executing A========"
                sh "mvn test"
                sleep 5
            }
        }
        stage("maven Build"){
            steps{
                echo "========executing A========"
                sh "mvn package"
                sleep 5
            }
        }
        stage("Deploy to Test Environment"){
            steps{
                echo "========executing A========"
                deploy adapters: [tomcat9(credentialsId: 'TOMCAT_DEVOPS', path: '', url: 'http://192.168.33.26:8080/')], contextPath: 'devops', war: '**/*.war'
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
