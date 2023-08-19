pipeline{
    agent any
    stages{
        stage("maven test"){
            steps{
                echo "========executing A========"
                sh "mvn test"
                sleep 10
            }
        }
        stage("maven Build"){
            steps{
                echo "========executing A========"
                sh "mvn package"
                sleep 10
            }
        }
        stage("Deploy to Test Environment"){
            steps{
                echo "========executing A========"
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
