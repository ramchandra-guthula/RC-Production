def mvn_home="/opt/maven"
pipeline {
    agent any
    
    environment {
        home_path = "/home/ec2-user"
    }
    
    stages {
        stage('work_space') {
            steps {
                echo "maven home path${mvn_home}"
                sh """ 
                ls -lrt ${env.home_path}
                echo 'this sample test'
                """
            }
        }
        stage('list'){
            steps{
                sh"ls -lrt"
            }
        }
    }
}
