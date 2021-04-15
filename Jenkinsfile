def mvn_home="/opt/maven"
pipeline {
    agent any
	parameters {
	  choice choices: ['PROD', 'UAT', 'IT', 'DEV'], description: 'Choose the  Environment', name: 'ENV'
	}
    environment {
        home_path = "/home/ec2-user"
		ENV = "${params.ENV}"
    }
    
    stages {
        
        stage('Clone repo'){
            steps{
                
            echo "===================We are cloning the GIT Repo============================\n"  
			echo "===================Running in ENV ${env.ENV}==============================\n"
            git credentialsId: 'ram_github_credentials', url: 'https://github.com/ramchandra-guthula/RC-Production.git'
            
            }
        }
        
        stage('work_space') {
            steps {
                echo "maven home path${mvn_home}"
                echo "Running in the Jenkins: ${JENKINS_URL}"
                echo "And the build number is: ${BUILD_NUMBER}"
            }
        }
        stage('list'){
            steps{
                script {
                foo = "bar"
            }
                sh"""
                ls -lrt
                echo "${foo}"
                """
            }
        }
    }
	 post {
        always {
            cleanWs()
        }
    }
}
